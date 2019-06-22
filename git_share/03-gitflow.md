# gitflow
 
 1. 简单介绍一下正常公司一个软件的环境
    1. 生产环境 prod
    2. 开发环境 dev
    3. 测试环境 sit (我司是sit和uat在一起的)
    4. 用户验收测试 uat 
 2. gitflow
    1. [安装](https://www.jianshu.com/p/714ba65e0e65)
    2. 不用专业的术语解释,用白话文
    3. [参考文章](https://blog.csdn.net/aaaaaaliang/article/details/79451598)
    4. 主要的线
        1. master
            * 生产的线
            * 最为稳定功能比较完整的随时可发布的代码，
                即代码开发完成，经过测试，没有明显的bug，
                才能合并到 master 中。
                请注意永远不要在 master 分支上直接开发和提交代码，
                以确保 master 上的代码一直可用；
        2. dev
            * 开发的线
            * 用作平时开发的主分支，并一直存在，
                永远是功能最新最全的分支，
                包含所有要发布 到下一个 release 的代码，主要用于合并其他分支，比如 feature 分支； 如果修改代码，新建 feature 分支修改完再合并到 develop 分支。所有的 feature、release 分支都是从 develop 分支上拉的。
        3. feature
            * 开发新功能
            * 这个分支主要是用来开发新的功能，一旦开发完成，通过测试没问题（这个测试，测试新功能没问题），我们合并回develop 分支进入下一个 release 。
        4. release
            * 测试
            * 用于发布准备的专门分支。当开发进行到一定程度，或者说快到了既定的发布日，可以发布时，建立一个 release 分支并指定版本号(可以在 finish 的时候添加)。开发人员可以对 release 分支上的代码进行集中测试和修改bug。（这个测试，测试新功能与已有的功能是否有冲突，兼容性）全部完成经过测试没有问题后，将 release 分支上的代码合并到 master 分支和 develop 分支。
        5. hotfix
            * 修复bug
            * 用于修复线上代码的bug。**从 master 分支上拉。**完成 hotfix 后，打上 tag 我们合并回 master 和 develop 分支。
    5. 注意事项
        * 所有开发分支从 develop 分支拉。
        * 所有 hotfix 分支从 master 拉。 
        * 所有在 master 上的提交都必要要有 tag，方便回滚。
        * 只要有合并到 master 分支的操作，都需要和 develop 分支合并下，保证同步。 
        * master 和 develop 分支是主要分支，主要分支每种类型只能有一个，派生分支每个类型可以同时存在多个。      