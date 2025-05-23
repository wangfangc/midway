# 介绍

Midway 是阿里巴巴 - 淘宝前端架构团队，基于渐进式理念研发的 Node.js 框架，通过自研的依赖注入容器，搭配各种上层模块，组合出适用于不同场景的解决方案。

Midway 基于 TypeScript 开发，结合了`面向对象（OOP + Class + IoC）`与`函数式（FP + Function + Hooks）`两种编程范式，并在此之上支持了 Web / 全栈 / 微服务 / RPC / Socket / Serverless 等多种场景，致力于为用户提供简单、易用、可靠的 Node.js 服务端研发体验。



## 为什么要有 Midway

社区上也有很多类似的框架，那为什么还需要 Midway ？

原因有三点：

1. Midway 是阿里内部一直持续在研发的框架，需要有面向应用层面的框架来和集团场景对接
2. 全量使用 TypeScript 是未来一段时间的趋势，面向未来去迭代和研发是作为架构组创新的要求
3. 虽然社区已经有 nest 这样的框架，但是这些产品的维护、协作、修改都会受到商业化产品的制约，也无法做到需求的快速迭代和安全性保障，整体的研发理念也和我们不同，为此，我们需要有一套自研的框架体系



## 我们的优势

1. Midway 框架是在内部已经使用 5 年以上的 Node.js 框架，有着长期投入和持续维护的团队做后盾
2. 已经在每年的大促场景经过考验，稳定性无须担心
3. 丰富的组件和扩展能力，例如数据库，缓存，定时任务，进程模型，部署以及 Web，Socket 甚至 Serverless 等新场景的支持
4. 一体化调用方案可以方便快捷和前端页面协同开发
5. 良好的 TypeScript 定义支持
6. 国产化文档和沟通容易简单



## 多编程范式

Midway 支持面向对象与函数式两种编程范式，你可以根据实际研发的需要，选择不同的编程范式来开发应用。



### 面向对象（OOP + Class + IoC）

Midway 支持面向对象的编程范式，为应用提供更优雅的架构。

下面是基于面向对象，开发路由的示例。
```typescript
// src/controller/home.ts
import { Controller, Get } from '@midwayjs/core';
import { Context } from '@midwayjs/koa';

@Controller('/')
export class HomeController {

  @Inject()
  ctx: Context

  @Get('/')
  async home() {
    return {
      message: 'Hello Midwayjs!',
      query: this.ctx.ip
    }
  }
}
```



### 函数式（FP + Function + Hooks）

Midway 也支持函数式的编程范式，为应用提供更高的研发效率。


下面是基于函数式，开发路由接口的示例。
```typescript
// src/api/index.ts

import { useContext } from '@midwayjs/hooks'
import { Context } from '@midwayjs/koa';

export default async function home () {
  const ctx = useContext<Context>()

  return {
    message: 'Hello Midwayjs!',
    query: ctx.ip
  }
}
```



## 环境准备工作


Midway 运行请预先安装 Node.js 环境和 npm，在国内可以使用 cnpm。


- 操作系统：支持 macOS，Linux，Windows
- 运行环境：建议选择 [LTS 版本](http://nodejs.org/)，最低要求 **12.11.0**。

在经过不断迭代之后，Midway 的版本要求如下：

| Midway 版本   | 开发环境 Node.js 版本要求 | 部署环境 Node.js 版本要求 |
| ------------- | ------------------------- | ------------------------- |
| >=v3.20.4     | >= v16，推荐 LTS 版本     | >= v16.20.2               |
| >=v3.9.0      | >= v14，推荐 LTS 版本     | >= v12.11.0               |
| 3.0.0 ~ 3.9.0 | >= v12，推荐 LTS 版本     | >= v12.0.0                |
| 2.x           | >= v12，推荐 LTS 版本     | >= v10.0.0                |

如果需要帮助，请参考 [如何安装 Node.js 环境](how_to_install_nodejs)。



## 正确的提问

- ✅  在 [github issue](https://github.com/midwayjs/midway/issues) 提问，可追踪，可沉淀，可 Star
  - 1、描述你的问题，提供尽可能详细的复现方法，框架版本，场景（Serverless 还是应用）
  - 2、尽可能提供报错截图，堆栈信息，最小复现的 repo



## 答疑分享群

群里会有热心的朋友，也会有新版本发布推送。

![image.png](https://img.alicdn.com/imgextra/i3/O1CN01LyI8r91S91RsKsD29_!!6000000002203-0-tps-3916-2480.jpg)



## 官方宣传渠道

- [哔哩哔哩](https://space.bilibili.com/1746017680)，会提供更新信息和教程

