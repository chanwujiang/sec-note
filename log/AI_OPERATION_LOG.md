# AI 操作日志

用于每次 AI 对接时快速了解上下文、操作记录和当前状态。

---

## 操作记录

### 2026-07-14 初次对接与笔记优化

#### 操作内容
- 读取 `F:\安全技术\笔记\note` 下所有学习笔记（docx/txt格式）
- 对比原始 docx 内容与 GitHub 仓库 `chanwujiang/sec-note` 版本的差异
- 对所有笔记进行内容融合：保留原始 docx 的详细度 + 补充现代化技术章节

#### 涉及文件

| 文件 | 操作 | 说明 |
|------|------|------|
| RCE.docx / RCE.md | 融合+扩展 | 原始（函数详解、测试技术）+ SSTI/表达式注入/Java Gadget/云原生/AI/WebShell原理/经典案例/防御 |
| CSRF.docx / CSRF.md | 融合+扩展 | 攻击流程详解、CSRF+XSS四种组合、HttpOnly讨论、Double Submit Cookie、FAQ |
| XSS学习笔记.docx / XSS学习笔记.md | 融合+扩展 | DOM型详解、事件标签大全、HttpOnly绕过5种方法、学习路线、Trusted Types/CSP Bypass |
| sql注入之sqlmap注入绕过waf.docx / 对应.md | 融合+扩展 | 完整参数表、自定义Tamper模板、Cloudflare/AWS绕过、NoSQL注入、AI辅助绕过 |
| 文件上传之基础及过滤方式.docx / 对应.md | 融合+扩展 | .user.ini绕过、数组拼接绕过、竞争条件代码、云存储/容器化攻击面 |
| Web安全实战进阶学习路线图.docx / 对应.md | 融合+扩展 | AI/LLM安全方向、云原生安全、红队自动化工具链 |
| 第一次流程.docx / 对应.md | 融合+扩展 | Lua Payload、HTTPS探测完整命令、渗透测试清单、Nuclei模板 |
| Windows批处理命令.txt / 对应.md | 格式优化+扩展 | PowerShell安全命令对照、AMSI绕过 |
| Markdown格式编写指南.md | 新增 | 从零教写Markdown笔记的指南 |

#### Git 操作
- 软回退 `git reset --soft 181bd88`（撤销 `f755e07` 提交，保留文件修改）
- 当前 HEAD 指向 `181bd88`（"增加第一次攻击"）
- 注意：`/md/` 文件夹内容已随回退消失

---

### 2026-07-16 第二次操作：完善 RCE 与文件包含漏洞

#### 涉及文件

| 文件 | 操作 | 新增内容 |
|------|------|---------|
| RCE.docx | 完整重写 | 保留原始全部内容（PHP/Java/Python/Node.js函数详解、基本+高级测试技术、自动检测工具(OWASP ZAP/Burp/Acunetix/SQLmap/Commix/Metasploit)、WAF绕过(分块传输/参数污染/动态载荷/无字母数字)、反序列化高级利用(Gadget Chain/ClassLoader/内存马)、框架中间件漏洞） + 补充(SSTI/表达式注入/云原生Docker&K8s/AI攻击面/Log4Shell/Struts2/Webmin案例/WebShell原理/POC&EXP方法论/防御方案）|
| 文件操作之文件包含漏洞.docx | 完整重写 | 保留原始全部内容（LFI/RFI分类、PHP伪协议利用链(php://filter/data://input://expect://)、日志注入(含自动化Python脚本)、Session投毒、图片马配合、RFI即时命令执行、后缀绕过(?/#/%00/路径长度)） + 补充(Zip包装器/Phar反序列化/编码绕过WAF/容器环境文件包含(K8s Secret)//proc/self利用/防御方案） |

---

### 2026-07-19 第三次操作：完善文件下载读取漏洞

#### 操作内容
- 读取日志了解前两次操作历史
- 比照 RCE.docx 等已完成文档的风格和结构
- 对 `文件操作之文件下载读取.docx` 进行完整重写

#### 涉及文件

| 文件 | 操作 | 说明 |
|------|------|------|
| 文件操作之文件下载读取.docx | 完整重写 | 保留原始全部内容（路径遍历基础、编码绕过、空字节截断、后缀绕过） + 补充（11大章：漏洞产生条件/4种语言危险函数详析/路径遍历6种绕过/WAF绕过6种技术/自动化工具/利用链/云存储OSS&S3&CDN&K8s&Serverless/AI&LLM Agent攻击面/防御方案含代码/6个CVE案例） |

#### 新增核心章节
- 云存储与容器环境：OSS Bucket配置不当、签名URL篡改、CDN回源穿透、K8s容器逃逸线索、Serverless临时凭证利用
- AI/LLM攻击面：Agent文件读取风险、AI生成的不安全代码模式对比、提示注入+文件读取复合攻击
- WAF绕过：HPP各服务器差异表、分块传输原理、Content-Type混淆、利用WAF自身解析缺陷
- 防御方案：白名单代码示例、路径规范化陷阱(os.path.join缺陷)、最小权限原则、RASP配置

#### 风格调整
- 去掉学习路线章节
- 每个绕过技术加原理说明
- 所有代码示例可直接复制使用

---

### 2026-07-19 第四次操作：完善逻辑越权（水平垂直越权）

#### 操作内容
- 读取原始 docx 内容（原始为简短问答风格笔记）
- 按照 RCE.docx 等已完成文档的详细展开风格重写
- 根据用户需求：去学习路线、全部写深、现代内容越多越好

#### 涉及文件

| 文件 | 操作 | 说明 |
|------|------|------|
| 逻辑越权之水平垂直越权.docx | 完整重写 | 保留原始全部核心要点（水平/垂直分类、冒用凭证特殊讨论） + 补充（10大章：权限验证基础/JWT越权5种/OAuth 2.0越权/微服务越权/云IAM越权/K8s RBAC/防御方案含代码/6个CVE案例/FAQ/自动化工具） |

#### 新增核心章节
- JWT越权：alg:none绕过、弱密钥破解、kid注入、Session Fixation关联
- OAuth 2.0越权：授权码拦截、CSRF+OAuth绑定、授权码重放、scope扩展
- 微服务架构越权：内部服务权限校验缺失、Token传递漏洞、Header注入
- 云环境IAM越权：AWS IAM策略过宽、STS代理权限提升、Bucket越权
- K8s RBAC：ServiceAccount权限过大、Pod API Server访问
- 防御方案：RBAC/ABAC模型、数据级权限校验、三账号测试流程
- FAQ：常见7问（含原始笔记核心问题"冒用凭证"的详细回答）

---

## 总结

> 所有笔记已基于原始docx内容完成完整升级，严格保留原始全部详细内容并在各章节补充了SSTI、云原生、AI攻击面等现代化内容；建立了AI操作日志体系便于后续无缝对接；md文件夹因git回退已清空待重建。
