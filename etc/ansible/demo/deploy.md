# deploy



直接将/etc/文件夹下面的文件拷贝到ansible部署机器上
进入/etc/ansible/中执行
## 测试脚本
`ansible-playbook -C redis-cluster.yml`
## 执行脚本
`ansible-playbook redis-cluster.yml`
## 清除环境
`ansible-playbook clean-redis-cluster.yml `

执行完毕在deploy节点的redis目录执行
`cd /root/redis/redis-4.0.11/src `
`./redis-trib.rb create --replicas 1 192.168.77.72:7001  192.168.77.73:7001  192.168.77.74:7001  192.168.77.75:7001  192.168.77.76:7001  192.168.77.77:7001  192.168.77.78:7001  192.168.77.79:7001`

网络不通需要修改防火墙策略