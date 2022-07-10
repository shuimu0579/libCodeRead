

# cac源码共读

- [cac问题](https://www.wolai.com/cuixiaorui/qKNw5XF2bYCYbxs7zBaiEN)
- [cac-github](https://github.com/cacjs/cac)

## .editorconfig  是干嘛的

- editorconfig是用于跨不同的编辑器和IDE为多个开发人员维护一致的编码风格的配置文件。

## .gitattributes 是干嘛的

- Git的gitattributes文件是一个文本文件，文件中的一行定义一个路径的若干属性。以行为单位设置一个路径下所有文件的属性。格式如下：要匹配的文件模式 属性1 属性2。

## 持续集成环境--circle.yml 是如何配置的

- circleci是一个云服务CI平台，可以帮助我们实现项目的持续集成，也就是所谓的CI。通过circleci我们只需要编写相关的配置文件即可，然后后续的测试、编译，发布等等都会通过circleci平台自动进行。

- [使用circleci + github实现前端项目自动化构建和部署](http://blog.yunishare.cn/2020/07/circle-github-setings.html)

## 分析一下单元测试环境是如何搭建的

### [ts-jest](https://github.com/kulshekhar/ts-jest) 是解决什么问题的? -- 一个支持source map的Jest转化器，让你使用Jest来测试用TypeScript编写的项目。

### 分析一下 [jest.config.js](https://jestjs.io/zh-Hans/docs/configuration#testenvironment-string)  这几个字段都有什么用?

- testEnvironment:用来进行单元测试的测试环境，默认为`node`
- transform:语法转换器，最终转换成js语法，供Jest使用。默认为`babel-jest`
- testRegex:检测哪些是单元测试文件
- testPathIgnorePatterns:哪些文件夹会跳过单元测试检测
- moduleFileExtensions: 如果你需要的模块没有指定文件扩展名，这些是Jest将寻找的扩展名，按照从左到右的顺序。

## [分析一下 package.json 里面的字段都是干嘛的](https://juejin.cn/post/7009826457010569223)

### [browser，module，main 字段优先级](https://github.com/SunshowerC/blog/issues/8)

- `main`字段。定义了 npm 包的CommonJS规范的入口文件
- `module`字段。 定义 npm 包的 ESM 规范的入口文件
- `browser`字段。定义 npm 包在 browser 环境下的入口文件。如果要在客户端使用模块，则应使用browser字段来代替main字段。

- `files`字段。files是一个文件数组，描述了将软件包作为依赖项安装时要包括的条目。
- `scripts`字段。scripts指定了运行脚本命令的npm命令行缩写
- `engines`字段。engines字段指明了该模块运行的平台，比如Node``的某个版本，或者npm的某个版本或者浏览器。
- `types`字段。指定ts版本的文件

## 写一个库的 README 需要哪几个部分?

- 项目背景、项目安装、项目示例或者用法、项目维护者、项目使用许可

- 有哪些可以快速生成 readme 的库
  - [readme-md-generator](https://github.com/kefranabg/readme-md-generator)
  - [markdown-toc](https://github.com/jonschlinkert/markdown-toc)

## [打包构建是如何做的？](https://rollupjs.org/guide/en/)-- 分析 rollup.config.js 

- `src/index.ts`作为入口文件，生成三种类型的出口文件：`dist/index.d.ts`（TS打包文件）、`dist/index.mjs`（ESModule打包文件）、`dist/index.js`（CommomJS打包文件）
- rollup将分散的代码块打包成一个[lib](https://github.com/rollup/rollup-starter-lib)或者一个[app](https://github.com/rollup/rollup-starter-app)。
- rollup.js返回一个对象，或者由对象组成的数组。其中对象里面的字段有如下三个：`input`、`output`、`plugins`

## [分析一下tsconfig里面的配置项](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

- tsconfig这个文件指定了哪些文件需要应用到这些编译规则。其中tsconfig这个文件里面包含`extends`、`compilerOptions`、`files`、 `include`、 `exclude`等文件
