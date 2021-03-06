# 领域建模

对于简单的业务领域，一个领域可能就是一个小的子域。领域建模过程相对简单，根据事件风暴可以分解出事件、命令、实体、聚合和限界上下文等，根据领域模型和微服务拆分原则设计出微服务即可。对于复杂的业务领域，领域可能还需要拆分为子域，甚至子域还会进一步拆分，如：保险领域可以拆分为承保、理赔、收付费和再保等子域，承保子域还可以再拆分为投保、保单管理等子子域。对于这种复杂的领域模型，是无法通过一个事件风暴完成领域建模的，即使能完成，其工程量也是非常浩大，效果也不一定好。

对于这种复杂的领域，我们可以分三阶段来完成领域模型和微服务设计。

- 拆分子域建立领域模型：根据业务特点考虑流程节点或功能模块等边界因素（微服务最终的拆分结果很多时候跟这些边界因素有一定的相关性），按领域逐级分解为大小合适的子域，针对子域进行事件风暴，记录领域对象、聚合和限界上下文，初步确定各级子域的领域模型。

- 领域模型微调：梳理领域内所有子域的领域模型，对各子域模型进行微调，这个过程重点考虑不同限界上下文内聚合的重新组合，同步需要考虑子域、限界上下文以及聚合之间的边界、服务以及事件之间的依赖关系，确定最终的领域模型。

- 微服务设计和拆分：根据领域模型的限界上下文和微服务的拆分原则，完成微服务的拆分和设计。
