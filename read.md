#### husky 版本7的正确使用方式
https://zhuanlan.zhihu.com/p/366786798



husky 是git 的 hooks, 
husky继承了Git下所有的钩子，在触发钩子的时候，husky可以阻止不合法的commit，push


#### commitlint
commitlint 是一种专门的commit规范 , 
husky校验的时候就会用到这个规范 ， 去跟用户提交的对比

type ：用于表明我们这次提交的改动类型，是新增了功能？还是修改了测试代码？又或者是更新了文档？总结以下 11 种类型：
build：主要目的是修改项目构建系统(例如 glup，webpack，rollup 的配置等)的提交
ci：主要目的是修改项目继续集成流程(例如 Travis，Jenkins，GitLab CI，Circle等)的提交
docs：文档更新
feat：新增功能
fix：bug 修复
perf：性能优化
refactor：重构代码(既没有新增功能，也没有修复 bug)
style：不影响程序逻辑的代码修改(修改空白字符，补全缺失的分号等)
test：新增测试用例或是更新现有测试
revert：回滚某个更早之前的提交
chore：不属于以上类型的其他类型(日常事务)


### 使用步骤
1,package.json 中 script添加
"prepare": "husky install"


2, git init 初始化git

3, 执行yarn安装

4 ,终端运行
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
