# GitHub 管理工具推荐

## 背景

在使用 GitHub 管理仓库时，需要在 Web 端创建远程仓库，在本地创建本地仓库，然后再用 `git remote add origin url` 进行关联。这个过程相对繁琐，而且还有优化的空间。如果频繁创建仓库，就更能发现这个痛点。

## 如何解决

我编写了一个操作 GitHub 的命令行工具 gh-cli，能够快速地创建远程仓库并与本地仓库关联。该工具使用 GitHub Open API，将需要的操作封装为 shell 脚本。gh-cli 的地址是 <https://github.com/Groos-dev/github-cli/tree/main>。如果觉得有用，欢迎给个 star。接下来介绍一下工具的基本用法。

## Install

```shel
curl -S https://raw.githubusercontent.com/Groos-dev/github-cli/refs/heads/main/gh_cli_installer.sh | bash
```

## How to use

- 创建仓库

会同时创建本地和远程的仓库，并关联二者，表现为如果当前有仓库名的目录是cd进目录，如果没有就创建，然后再创建远程仓库并与本地仓库相关联

```shell
gh-cli create repo001 -d "This is a description text." 
```

- 删除仓库

```shell
gh-cli delete repo001 
```

- 更新工具

```shell
gh-cli update-cli
```

- other

其他功能目前自己没需求所以没开发，如果有读者需要某个功能欢迎提[issue](https://github.com/Groos-dev/github-cli/issues)，此外代码写的有点随意，勿喷！！！
