# 虎皮椒支付集成指南

## 概述

Immerse 使用虎皮椒（XunHuPay）作为支付网关，支持微信支付和支付宝。

## 前置条件

1. 注册虎皮椒账号：https://www.xunhupay.com
2. 申请微信支付/支付宝支付渠道并完成签约
3. 获取 APPID 和 APPSECRET

---

## Supabase 环境变量配置

在 Supabase Dashboard -> Project Settings -> Edge Functions 中配置以下环境变量：

```bash
# 虎皮椒支付凭证
XUNHUPAY_APPID=你的应用ID
XUNHUPAY_APPSECRET=你的应用密钥

# Supabase 配置（通常已自动设置）
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```

---

## 部署 Edge Functions

```bash
# 进入 supabase 目录
cd immerse/supabase

# 部署创建订单函数
supabase functions deploy create-order

# 部署支付回调 Webhook
supabase functions deploy payment-webhook
```

---

## 虎皮椒后台配置

1. 登录虎皮椒后台
2. 进入「应用管理」
3. 配置异步通知 URL：
   ```
   https://your-project.supabase.co/functions/v1/payment-webhook
   ```

---

## 数据库迁移

确保已运行订单表迁移：

```bash
supabase db push
```

或手动执行 `migrations/003_orders_table.sql`

---

## 产品配置

在 `create-order/index.ts` 中定义的产品：

| productId | 名称 | 价格 | 天数 |
|-----------|------|------|------|
| pro_monthly | Pro 月度会员 | ¥6 | 30 |
| pro_yearly | Pro 年度会员 | ¥58 | 365 |
| ultra_monthly | Ultra 月度会员 | ¥12 | 30 |
| ultra_yearly | Ultra 年度会员 | ¥108 | 365 |

---

## 支付流程

```
用户点击升级 
  -> 前端调用 create-order Edge Function
  -> 后端创建虎皮椒订单并返回支付链接
  -> 用户跳转支付页面完成支付
  -> 虎皮椒回调 payment-webhook
  -> 后端验证签名并更新用户订阅状态
  -> 前端轮询订单状态并显示成功提示
```

---

## 测试支付

虎皮椒支持沙箱测试环境，可在后台开启测试模式。

---

## 故障排查

1. **签名验证失败**：检查 APPSECRET 是否正确
2. **回调未触发**：检查 notify_url 是否可访问
3. **订单状态未更新**：查看 Supabase Edge Function 日志
