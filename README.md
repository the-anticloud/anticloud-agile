# AGILE

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-oil_gas-lightgrey)

> Anticloud-hardened packaging of the upstream project `AGILE` in category **OIL GAS**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** OIL GAS · **Upstream:** https://github.com/valarchie/AgileBoot-Back-End · **Upstream pin:** `4e9ab30d68f2cb9dce6d9fc772456bcd106d575f` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

<p align="center">
      <img src="https://img.shields.io/badge/Release-V1.8.0-green.svg" alt="Downloads">
      <img src="https://img.shields.io/badge/JDK-1.8+-green.svg" alt="Build Status">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Build Status">
   <img src="https://img.shields.io/badge/Spring%20Boot-2.7.1-blue.svg" alt="Downloads">
   <a target="_blank" href="https://bladex.vip">
   <img src="https://img.shields.io/badge/Author-valarchie-ff69b4.svg" alt="Downloads">
 </a>
 <a target="_blank" href="https://bladex.vip">
   <img src="https://img.shields.io/badge/Copyright%20-@Agileboot-%23ff3f59.svg" alt="Downloads">
 </a>
 </p>  
<p align="center">

<img alt="logo" height="200" src="https://oscimg.oschina.net/oscnet/up-eda2a402cc061f1f5f40d9ac4c084f4c98c.png">
</p>
<h1 align="center" style="margin: 30px 0 30px; font-weight: bold;">AgileBoot v2.0.0 </h1>
<h4 align="center">基于SpringBoot+Vue3前后端分离的Java快速开发脚手架</h4>
<p align="center">
</p>

## ⚡平台简介⚡

AgileBoot是一套开源的全栈精简快速开发平台，毫无保留给个人及企业免费使用。本项目的目标是做一款精简可靠，代码风格优良，项目规范的小型开发脚手架。
适合个人开发者的小型项目或者公司内部项目使用。也可作为供初学者学习使用的案例。

* 前端是基于优秀的开源项目[Pure-Admin](https://github.com/pure-admin/vue-pure-admin)开发而成。在此感谢Pure-Admin作者。
* 前端采用Vue3、Element Plus、TypeScript、Pinia。对应前端仓库 [AgileBoot-Front-End](https://github.com/valarchie/AgileBoot-Front-End) ，保持同步更新。
* 后端采用Spring Boot、Spring Security & Jwt、Redis & MySql、Mybatis Plus、Hutool工具包。
* 权限认证使用Jwt，支持多终端认证系统。
* 支持注解式主从数据库切换，注解式请求限流，注解式重复请求拦截。
* 支持注解式菜单权限拦截，注解式数据权限拦截。
* 支持加载动态权限菜单，实时权限控制。
* ***有大量的单元测试，集成测试覆盖确保业务逻辑正确***。

***V1.0.0版本使用JS开发，V2.0.0版本使用TS开发***。  
***V1.0.0地址：[后端(AgileBoot-Back-End-Basic)](https://github.com/valarchie/AgileBoot-Back-End-Basic) -  [前端(AgileBoot-Front-End-Basic)](https://github.com/valarchie/AgileBoot-Front-End-Basic)***

> 有任何问题或者建议，可以在 _Issues_ 中提给作者。  
> 
> 您的Issue比Star更重要
>
> 如果觉得项目对您有帮助，可以来个Star ⭐

## 💥 在线体验 💥
演示地址：
- www.agileboot.vip
- www.agileboot.cc
>  账号密码：admin/admin123

## 🌴 项目背景 🌴
业余时间想做一些个人小项目，一开始找了很多开源项目比如Ruoyi / Jeecg / ElAdmin / RenRen-Fast / Guns / EAdmin  
最后本项目选择基于Ruoyi项目进行完全重构改造。  
首先非常感谢Ruoyi作者。但是Ruoyi项目存在太多缺陷。
- 命名比较乱七八糟（很多很糟糕的命名，包括机翻英语乱用）
- 项目分包以及模块比较乱
- 比较原始的Controller > Service > DAO的开发模式。过于面向过程。
- 一大堆自己造的轮子，并且没有UT覆盖。
- 大量逻辑嵌套在if else块当中
- 值的前后不统一，比如有的地方1代表是，有的地方1代表否
- 很多很奇怪的代码写法（比如return result > 0 ? true:false..    一言难尽）
- 业务逻辑不集中，代码可读性较差。

于是我做了大量的重构工作。

### 重构内容

- 规范：
    - 切分不同环境的启动文件
    - 统一设计异常类
    - 统一设计错误码并集中处理异常
    - 统一系统内的变量并集中管理
    - 统一返回模型
    - 引入Google代码格式化模板
    - 后端代码的命名基本都整改OK
    - 前端代码的命名也非常混乱，进行了整改
    - 规范系统内的常量
- 整改：
    - 引入hutool包以及guava包去掉大量自己造的轮子，尽可能使用现成的轮子
    - 去除代码中大量的warning
    - 引入lombok去除大量getter setter代码
    - 调整日志级别
    - 字典类型数据完全用Enum进行代替
    - 移除SQL注入的Filter，因为迁移到Mybatis Plus就不会有这个注入的问题
    - XSS直接通过JSON序列化进行转义。
    - 替换掉很多Deprecated的类以及配置
    - 替换fastJson为Jackson
    - 数据库的整体重构设计，缩减至10张表。
    - 重新设计异步代码
    - 前后端密码加密传输（更严谨的话，还是需要HTTPS）
    - 重构权限校验和数据权限校验（直接都通过注解的形式）
- 优化：
    - 优化异步服务
    - 优化Redis缓存类，封装各个业务缓存，提供多级缓存实现（Redis+Guava）
    - 提供三个层级的缓存供使用者调用（Map,Guava,Redis使用者可依情况选择使用哪个缓存类）
    - 权限判断使用多级缓存
    - IP地址查询引入离线包
    - 前端优化字典数据缓存
    - 启动优化
    - i18n支持
    - 优化excel工具类，代码更加简洁
    - 将所有逻辑集中于Domain模块中
    - 切面记录修改者和创建者
    - 统一设置事务

## ✨ 使用 ✨

### 开发环境

- JDK
- Mysql
- Redis
- Node.js

### 技术栈

| 技术             | 说明              | 版本                |
|----------------|-----------------|-------------------|
| `springboot`   | Java项目必备框架      | 2.7               |
| `druid`        | alibaba数据库连接池   | 1.2.8             |
| `springdoc`    | 文档生成            | 3.0.0             |
| `mybatis-plus` | 数据库框架           | 3.5.2             |
| `hutool`       | 国产工具包（简单易用）     | 3.5.2             |
| `mockito`      | 单元测试模拟          | 1.10.19           |
| `guava`        | 谷歌工具包（提供简易缓存实现） | 31.0.1-jre        |
| `junit`        | 单元测试            | 1.10.19           |
| `h2`           | 内存数据库           | 1.10.19           |
| `jackson`      | 比较安全的Json框架     | follow springboot |
| `knife4j`      | 接口文档框架          | 3.0.3             |
| `Spring Task`  | 定时任务框架（适合小型项目）  | follow springboot |

### 启动说明

#### 前置准备： 下载前后端代码

```
git source https://github.com/valarchie/AgileBoot-Back-End
git source https://github.com/valarchie/AgileBoot-Front-End
```

#### 安装好Mysql和Redis

#### 后端启动
```
1. 生成所需的数据库表
找到后端项目根目录下的sql目录中的agileboot_xxxxx.sql脚本文件(取最新的sql文件)。 导入到你新建的数据库中。

2. 在admin模块底下，找到resource目录下的application-dev.yml文件
配置数据库以及Redis的 地址、端口、账号密码

3. 在根目录执行mvn install

4. 找到agileboot-admin模块中的AgileBootAdminApplication启动类，直接启动即可

5. 当出现以下字样即为启动成功
  ____   _                _                                                           __         _  _ 
 / ___| | |_  __ _  _ __ | |_   _   _  _ __    ___  _   _   ___  ___  ___  ___  ___  / _| _   _ | || |
 \___ \ | __|/ _` || '__|| __| | | | || '_ \  / __|| | | | / __|/ __|/ _ \/ __|/ __|| |_ | | | || || |
  ___) || |_| (_| || |   | |_  | |_| || |_) | \__ \| |_| || (__| (__|  __/\__ \\__ \|  _|| |_| || ||_|
 |____/  \__|\__,_||_|    \__|  \__,_|| .__/  |___/ \__,_| \___|\___|\___||___/|___/|_|   \__,_||_|(_)
                                      |_|                             

```

#### 前端启动
详细步骤请查看对应前端部分

```
1. pnpm install

2. pnpm run dev

3. 当出现以下字样时即为启动成功

vite v2.6.14 dev server running at:

> Local: http://127.0.0.1:80/

ready in 4376ms.

```

详细过程在这个文章中：[AgileBoot - 手把手一步一步带你Run起全栈项目(SpringBoot+Vue3)](https://juejin.cn/post/7153812187834744845)

> 对于想要尝试全栈项目的前端人员，这边提供更简便的后端启动方式，无需配置Mysql和Redis直接启动
#### 无Mysql/Redis 后端启动
```
1. 找到agilboot-admin模块下的resource文件中的application.yml文件

2. 配置以下两个值
spring.profiles.active: basic,dev
改为
spring.profiles.active: basic,test

agileboot.embedded.mysql: false
agileboot.embedded.redis: false
改为
agileboot.embedded.mysql: true
agileboot.embedded.redis: true

请注意:高版本的MacOS系统，无法启动内置的Redis

3. 找到agileboot-admin模块中的AgileBootAdminApplication启动类，直接启动即可
```

## 🙊 系统内置功能 🙊  
  

🙂 大部分功能，均有通过 **单元测试** **集成测试** 保证质量。

|     | 功能    | 描述                              |
|-----|-------|---------------------------------|
|     | 用户管理  |

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Java / Maven** (manifests: pom.xml; scanned in UPSTREAM_CLONE)
- Top-level source layout: `agileboot-admin/`, `agileboot-api/`, `agileboot-common/`, `agileboot-domain/`, `agileboot-infrastructure/`, `bin/`, `docker/`, `sql/`
- Snapshot size: **347 files**, **19363 lines of code** (measured; see Benchmarks)
- Primary languages: `.java` (311), `.xml` (9), `.yml` (7), `.sql` (6), `(none)` (3), `.md` (3)
- Upstream commit pinned for this packaging: `4e9ab30d68f2cb9dce6d9fc772456bcd106d575f`

---

## Installation

<img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Build Status">
   <img src="https://img.shields.io/badge/Spring%20Boot-2.7.1-blue.svg" alt="Downloads">
   <a target="_blank" href="https://bladex.vip">
   <img src="https://img.shields.io/badge/Author-valarchie-ff69b4.svg" alt="Downloads">
 </a>
 <a target="_blank" href="https://bladex.vip">
   <img src="https://img.shields.io/badge/Copyright%20-@Agileboot-%23ff3f59.svg" alt="Downloads">
 </a>
 </p>  
<p align="center">

<img alt="logo" height="200" src="https://oscimg.oschina.net/oscnet/up-eda2a402cc061f1f5f40d9ac4c084f4c98c.png">
</p>
<h1 align="center" style="margin: 30px 0 30px; font-weight: bold;">AgileBoot v2.0.0 </h1>
<h4 align="center">基于SpringBoot+Vue3前后端分离的Java快速开发脚手架</h4>
<p align="center">
</p>

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

No usage section was found in the upstream readme. Entry points detected in this project directory:

Browse the snapshot layout listed under What This Project Does and follow the upstream run instructions for the detected ecosystem (Java / Maven).

Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

|     | 服务监控  | 监视当前系统CPU、内存、磁盘、堆栈等相关信息         |
|     | 缓存监控  | 对系统的缓存信息查询，命令统计等                |
|     | 连接池监视 | 监视当前系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈 |

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Java / Maven |
| Manifests detected | pom.xml |
| Files in snapshot | 347 |
| Lines of code | 19363 |
| Dependency references | 0 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

- 请导入统一的代码格式化模板（Google）: Settings > Editor > Code Style > Java > 设置按钮 > import schema > 选择项目根目录下的GoogleStyle.xml文件
- 如需要生成新的表，请使用CodeGenerator类进行生成。
  - 填入数据库地址，账号密码，库名。然后填入所需的表名执行代码即可。（大概看一下代码就知道怎么填啦）
  - 生成的类在infrastructure模块下的target/classes目录下
  - 不同的数据库keywordsHandler方法请填入对应不同数据库handler。（搜索keywordsHandler关键字）
- 项目基础环境搭建，请参考docker目录下的指南搭建。保姆级启动说明：
  - [AgileBoot - 手把手一步一步带你Run起全栈项目(SpringBoot+Vue3)](https://juejin.cn/post/7153812187834744845)
- 注意：管理后台的后端启动类是AgileBoot**Admin**Application
- Swagger的API地址为 http://localhost:8080/v3/api-docs

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `AGILE` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
MIT License

Copyright (c) 2022 valarchie

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `AGILE` (category: OIL GAS)
- **Upstream URL:** https://github.com/valarchie/AgileBoot-Back-End
- **Pinned commit (SHA):** `4e9ab30d68f2cb9dce6d9fc772456bcd106d575f`
- **Branch:** main
- **Pin provenance:** GitHub API commits/main. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`305f3bfec7c5ae1290c62b2aa43aeec3ab33c6d504dff0dc7f0952d5770d79e0`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| DANS (KNAW/NWO, Netherlands) | 10.17026/PT | EU-recognised archive |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe
and Mail, Business Insider, National Post, Financial Post, StreetInsider,
Digital Journal, Barchart, International Business Times, and Fox News.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

