这个项目是根据业务场景编写的jenkinsfile，主要用在k8s上跑的微服务，希望对你有些启发。
===================================================================================

## jenkinsfiles： 
+ 典型的jenkinsfile发出来给大家分享下。 
|  FILE   | Description  |
|  ----  | ----  |
| main.jenkinsfile  | 主要jenkinsfile文件，微服务程序部署 |
| mavenInstall.jenkinsfile  | 依赖包打包 |
| staticWebsite.jenkinsfile  | 静态页面更新至nginx下，并reload |
| npmWebsite.jenkinsfile  | npm 前端项目构建，并打包放置到nginx下 |

## resources：  这属于共享库代码，需要在系统中配置共享库地址及名称
### resources中根据目录区分项目环境，例如生产prod，预生产preprod等
+ conf：在相应conf目录下每个项目服务都有与项目名称对应的配置文件，格式为groovy格式
+ dockerfile： 存放构建项目的dockerfile，如果有特殊需要的dockerfile，以项目名称为前缀生成文件，main.jenkinsfile中做判断，并自动调用
+ yaml： 这里存放k8s的deployment及service的yaml文件，特殊需求同上。

## src： 这属于共享库代码，需要在系统中配置共享库地址及名称
+ 一些公共方法。
