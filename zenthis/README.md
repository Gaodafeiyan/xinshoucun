# 认购专区 Flutter 前端

这是一个用于展示和管理认购计划的Flutter应用程序。

## 功能特性

- 📱 现代化的移动端界面
- 🔐 用户认证和授权
- 💰 钱包余额管理
- 📋 认购计划浏览
- 📦 订单管理
- 🔄 实时数据刷新

## 技术栈

- **Flutter**: 跨平台移动应用框架
- **Dio**: HTTP客户端
- **Go Router**: 路由管理
- **Provider**: 状态管理
- **Shared Preferences**: 本地存储

## 项目结构

```
lib/
├── core/
│   └── http_client.dart          # HTTP客户端配置
├── services/
│   ├── wallet_service.dart       # 钱包服务
│   └── subscription_service.dart # 认购服务
├── pages/
│   └── subscription/
│       └── subscription_page.dart # 认购专区页面
└── main.dart                     # 应用入口
```

## 安装和运行

### 前置要求

- Flutter SDK (3.8.1+)
- Dart SDK
- Android Studio / VS Code
- 后端API服务运行在 `http://localhost:1337`

### 安装步骤

1. **安装依赖**
   ```bash
   cd zenthis
   flutter pub get
   ```

2. **运行应用**
   ```bash
   flutter run
   ```

3. **构建发布版本**
   ```bash
   flutter build apk
   flutter build ios
   ```

## API 集成

### 后端API端点

- `GET /api/qianbao-yues/test` - 测试API连接
- `GET /api/qianbao-yues/user-wallet` - 获取用户钱包
- `GET /api/qianbao-yues/token-balances` - 获取代币余额
- `GET /api/dinggou-jihuas` - 获取认购计划列表
- `GET /api/dinggou-dingdans` - 获取用户订单
- `POST /api/dinggou-dingdans` - 创建认购订单

### 错误处理

应用包含完整的错误处理机制：

- 网络连接错误
- API认证失败
- 服务器错误
- 数据验证错误

## 主要功能

### 1. 认购计划浏览
- 显示所有可用的认购计划
- 计划详情包括金额、收益、期限
- 实时状态更新

### 2. 订单管理
- 查看个人认购订单
- 订单状态跟踪
- 取消待支付订单

### 3. 钱包集成
- 显示USDT和AI代币余额
- 支持多种代币类型
- 余额实时更新

## 开发指南

### 添加新页面

1. 在 `lib/pages/` 下创建新页面
2. 在 `main.dart` 中添加路由配置
3. 更新导航逻辑

### 添加新服务

1. 在 `lib/services/` 下创建服务类
2. 实现API调用方法
3. 添加错误处理

### 测试

运行测试脚本：
```bash
dart test_frontend_integration.dart
```

## 故障排除

### 常见问题

1. **API连接失败**
   - 检查后端服务是否运行
   - 确认API地址配置正确
   - 检查网络连接

2. **认证失败**
   - 确认用户已登录
   - 检查token是否有效
   - 重新登录

3. **数据加载失败**
   - 检查API响应格式
   - 确认数据字段名称
   - 查看控制台错误信息

### 调试模式

启用详细日志：
```dart
// 在 http_client.dart 中启用详细日志
print('🌐 API请求: ${options.method} ${options.path}');
print('✅ API响应: ${response.statusCode} ${response.requestOptions.path}');
print('❌ API错误: ${error.response?.statusCode} ${error.requestOptions.path}');
```

## 部署

### Android
```bash
flutter build apk --release
```

### iOS
```bash
flutter build ios --release
```

### Web
```bash
flutter build web --release
```

## 贡献

1. Fork 项目
2. 创建功能分支
3. 提交更改
4. 推送到分支
5. 创建 Pull Request

## 许可证

MIT License
