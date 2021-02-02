* [1、在 setting 里点击 new ssh key](#1%E5%9C%A8-setting-%E9%87%8C%E7%82%B9%E5%87%BB-new-ssh-key)
* [2、打开 git bash](#2%E6%89%93%E5%BC%80-git-bash)
  * [2\.1 将现有的 ssh key 删掉](#21-%E5%B0%86%E7%8E%B0%E6%9C%89%E7%9A%84-ssh-key-%E5%88%A0%E6%8E%89)
  * [2\.2 生成新的 ssh key](#22-%E7%94%9F%E6%88%90%E6%96%B0%E7%9A%84-ssh-key)
  * [2\.3 一路回车](#23-%E4%B8%80%E8%B7%AF%E5%9B%9E%E8%BD%A6)
  * [2\.4 查看并复制 ssh key](#24-%E6%9F%A5%E7%9C%8B%E5%B9%B6%E5%A4%8D%E5%88%B6-ssh-key)
  * [2\.5 验证](#25-%E9%AA%8C%E8%AF%81)

# 1、在 `setting` 里点击 `new ssh key`

![image-20210202113645001](https://gitee.com/li_hao_qi/imgbed/raw/master/img/20210202113645.png)

![image-20210202114246730](https://gitee.com/li_hao_qi/imgbed/raw/master/img/20210202114246.png)

# 2、打开 `git bash`

## 2.1 将现有的 ssh key 删掉

```shell
rm -rf ~/.ssh/*
```

## 2.2 生成新的 ssh key

```shell
ssh-keygen -t rsa -b 4096 -C "你的邮箱"
```

## 2.3 一路回车

![image-20210202113954627](https://gitee.com/li_hao_qi/imgbed/raw/master/img/20210202113954.png)

## 2.4 查看并复制 ssh key

```shell
cat ~/.ssh/id_rsa.pub
```

回到 1 ，在 titile 里起个名字，将复制的东西复制在 key 里面。

![image-20210202114200919](https://gitee.com/li_hao_qi/imgbed/raw/master/img/20210202114200.png)

点击添加

## 2.5 验证

```shell
ssh -T git@github.com
```

看到

![image-20210202114413750](https://gitee.com/li_hao_qi/imgbed/raw/master/img/20210202114413.png)

输入 yes 回车

如果出现 `git@github.com: Permission denied (publickey).` 说明失败

**重新回1来**

如果出现 `Hi devbzx! You've successfully authenticated, but GitHub does not provide shelaccess.` 说明成功，可以直接使用 `ssh` 进行 `push`