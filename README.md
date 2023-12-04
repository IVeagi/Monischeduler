# Monischeduler
this is  a scheduler for kuberneters , base on monitor data, force on 
1 根据集群表述，不参与kube-scheduler调度，不是对应步骤的插件
2.首先对集群进行规范化，设置pod的优先级，根据业务决定是否支持抢占
3.以cronjob方式运行，触发阈值小于集群自身机制 然后根据监控情况，和pod的优先级，QPS ，业务优先级 打分，根据评分选择将要驱逐的pod
4.根据符合需求的node的监控数据，选择是否驱逐pod，
5.驱逐前设置节点不可调度，驱逐后重新拉起
