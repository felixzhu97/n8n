# n8n TOGAF 企业架构图

本目录包含n8n平台的完整TOGAF（The Open Group Architecture Framework）企业架构图，使用PlantUML格式绘制。

## 文件说明

### 语言版本

所有架构图提供中文和英文两个版本：
- **中文版本**：`*-architecture.puml`（如 `business-architecture.puml`）
- **英文版本**：`*-architecture-en.puml`（如 `business-architecture-en.puml`）

### 1. business-architecture.puml / business-architecture-en.puml
**业务架构图** - 描述n8n的业务能力、业务流程和业务服务

包含：
- **业务能力视图**：工作流自动化、集成能力、数据处理、AI/ML能力、协作能力、监控分析
- **业务流程视图**：工作流设计流程、执行流程、凭证管理流程、用户管理流程、错误处理流程
- **业务服务视图**：工作流管理服务、执行管理服务、用户管理服务、凭证管理服务、节点管理服务、协作服务、通知服务

### 2. application-architecture.puml / application-architecture-en.puml
**应用架构图** - 描述n8n的应用组件、应用交互和应用服务

包含：
- **前端应用层**：Editor UI (Vue 3)、Design System、i18n
- **后端应用层**：CLI Server、REST API、WebSocket Server、Webhook Server、Public API
- **核心引擎层**：Workflow Engine、Execution Engine、Node Execution、Routing Node、Triggers & Pollers
- **节点系统层**：Nodes Base、LangChain Nodes、Community Nodes、Node Registry
- **应用服务层**：各种业务服务实现
- **数据访问层**：Repository Pattern、TypeORM

### 3. data-architecture.puml / data-architecture-en.puml
**数据架构图** - 描述n8n的数据模型、数据流和数据存储

包含：
- **核心数据模型**：WorkflowEntity、ExecutionEntity、CredentialsEntity、User、Project、Folder、TagEntity等
- **关联数据模型**：SharedWorkflow、SharedCredentials、WorkflowHistory、WebhookEntity、BinaryDataFile等
- **数据流视图**：工作流设计数据流、执行数据流、凭证数据流、二进制数据流
- **数据存储视图**：SQLite/PostgreSQL/MySQL、Redis缓存、文件存储
- **数据访问层**：TypeORM、Repository Pattern

### 4. technology-architecture.puml / technology-architecture-en.puml
**技术架构图** - 描述n8n的技术组件、部署架构和技术平台

包含：
- **运行时环境**：Node.js、TypeScript
- **Web框架层**：Express、中间件、WebSocket
- **数据持久化层**：TypeORM、SQLite/PostgreSQL/MySQL
- **缓存与队列层**：Redis、Bull Queue、Cache Manager
- **认证与安全层**：JWT、OAuth、密码加密、MFA、SAML
- **构建与工具链**：pnpm、Turbo、TypeScript Compiler、Vite、Biome、ESLint
- **测试框架**：Jest、Vitest、Playwright、Nock
- **监控与可观测性**：Prometheus、Sentry、PostHog、日志系统
- **部署架构**：Docker容器、单机部署、队列模式、任务运行器

### 5. overall-architecture.puml / overall-architecture-en.puml
**总体架构图** - 整合所有TOGAF视图的架构全景

展示：
- 四个架构层（业务、应用、数据、技术）之间的关系
- 层次间的依赖和交互
- 外部接口和用户交互
- 关键数据流和架构原则

## 如何使用

### 查看图表

1. **在线查看**：
   - 访问 [PlantUML在线服务器](http://www.plantuml.com/plantuml/uml/)
   - 复制`.puml`文件内容到在线编辑器
   - 或使用支持PlantUML的IDE插件（如VS Code的PlantUML扩展）

2. **本地生成图片**：
   ```bash
   # 安装PlantUML（需要Java）
   # macOS
   brew install plantuml
   
   # 生成PNG图片
   plantuml business-architecture.puml
   
   # 生成SVG图片
   plantuml -tsvg business-architecture.puml
   ```

3. **VS Code插件**：
   - 安装 "PlantUML" 扩展
   - 打开`.puml`文件
   - 使用 `Alt+D` 预览图表

### 编辑图表

所有图表使用标准PlantUML语法，可以直接编辑`.puml`文件。主要语法元素：
- `component` - 组件
- `package` - 包/分组
- `class` - 类（用于数据模型）
- `database` - 数据库
- `node` - 节点（用于部署）
- `-->` - 关系箭头
- `note` - 注释

## 架构层次说明

### 业务架构层
定义"做什么"（What）：
- 业务能力和业务流程
- 业务服务和业务价值
- 业务规则和约束

### 应用架构层
定义"如何实现业务"（How）：
- 应用组件和模块
- 应用交互和接口
- 应用服务和功能

### 数据架构层
定义"数据如何组织"（Data）：
- 数据模型和实体
- 数据流和转换
- 数据存储和访问

### 技术架构层
定义"技术如何支撑"（Technology）：
- 技术栈和平台
- 基础设施和部署
- 工具链和开发环境

## 架构原则

1. **分层架构**：清晰的层次划分，每层关注点分离
2. **依赖倒置**：上层依赖下层，下层不依赖上层
3. **接口抽象**：通过接口和抽象层实现解耦
4. **可扩展性**：支持水平扩展和垂直扩展
5. **可维护性**：模块化设计，便于维护和演进

## 更新说明

这些架构图基于n8n当前代码库生成，反映了实际的系统架构。当系统架构发生变化时，应同步更新相应的架构图。

## 参考资源

- [TOGAF标准](https://www.opengroup.org/togaf)
- [PlantUML文档](https://plantuml.com/)
- [n8n架构文档](../AGENTS.md)

