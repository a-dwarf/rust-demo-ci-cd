# rust-demo-ci-cd

1. 新建项目

https://github.com/a-dwarf/rust-demo-ci-cd

2. 本地新建rust工程

`cargo new rust-demo-ci-cd`

`cargo run`

3. github

   ```
   echo "# rust-demo-ci-cd" >> README.md
   git init
   git add README.md
   git commit -m "first commit"
   git branch -M main
   git remote add origin https://github.com/a-dwarf/rust-demo-ci-cd.git
   git push -u origin main
   ```

4. 使用[ssh-action](https://github.com/appleboy/ssh-action), 其中：

   - host：为自己主机的地址，这里设置在了项目的secrets中
   - username： 为主机ssh的用户名，同样写在了项目的secrets中
   - key：为登录主机的私钥

5. 处于安全性的考虑，使用GitHub的Secrets。 在项目的Settings->Secrets->Actions增加私钥

6. 添加actions,一般选推荐的，也可以在手动创建.github/workflows/deploy.yml

   https://github.com/a-dwarf/rust-demo-ci-cd/actions/new
