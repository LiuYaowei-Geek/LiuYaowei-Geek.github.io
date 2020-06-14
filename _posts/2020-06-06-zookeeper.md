---
layout: post
title: "zookeeper"
excerpt: "learning zookeeper"
categories:
  - middleware
tags:
  - zookeeper
  - middleware
---

* [ZooKeeper](#zookeeper)
   * [zookeeperCMD](#zookeepercmd)
   * [简介](#简介)
# ZooKeeper
## zookeeperCMD
1. 启动服务端：`zkServer.cmd`
2. 启动客户端：`zkCli.cmd -server 127.0.0.1:2181`
3. 查看：`ls /`
4. zk admin prot：`8089`
5. elastic zk node：`[config, instances, leader, servers, sharding]`

## 简介
分布式服务框架，为分布式应用提供一致性协调服务的中间件；用来解决分布式应用中经常遇到的数据管理问题，如：统一命名服务、状态同步服务、集群管理和分布式应用配置项的管理。  
zookeeper=文件系统+监听通知机制。  
>文件系统：  
Zookeeper提供一个多层级的节点命名空间（节点称为znode）。与文件系统不同的是，这些节点都可以设置关联的数据，而文件系统中只有文件节点可以存放数据而目录节点不行。Zookeeper为了保证高吞吐和低延迟，在内存中维护了这个树状的目录结构，这种特性使得Zookeeper不能用于存放大量的数据，每个节点的存放数据上限为1M。  
>通知机制：  
client端会对某个znode建立一个watcher事件，当该znode发生变化时，这些client会收到zk的通知，然后client可以根据znode变化来做出业务上的改变等。