# Elastic Container Service (ECS)

Services run Tasks. Tasks are associated with specific container tags.

Service Discovery, Load Balancers, Listener Rules

[This post](https://tomgregory.com/aws-ecs-deployments-step-by-step/) covers a full ECS setup.

## Service Updates

> If a service is using the rolling update (ECS) deployment type, the minimum healthy percent represents a lower limit on the number of tasks in a service that must remain in the RUNNING state during a deployment, as a percentage of the desired number of tasks (rounded up to the nearest integer). 

For example, consider this CloudFormation fragment:
```yml
  ServiceName: !Ref 'AWS::StackName'
  Cluster: !Ref 'ClusterName'
  DesiredCount: !Ref 'AppInstances'
  DeploymentConfiguration:
    MaximumPercent: 200
    MinimumHealthyPercent: 100
```

## Rollbacks

ECS deploys versions of tasks. Tasks are associated with a version of a container. To rollback to a previous version of a task after a deployment, update the service and choose a previous task version. Check "force new deployemnt". This will trigger a deployment of the previous task version.

## Debug Deployments

Services run version of tasks. Tasks may fail to start. 

Under Health and Metrics in ECS, you can see when new tasks are started. To find the reason that a task failed to start, navigate to the cluster in ECS and click Tasks. Find the task ID that failed to start (sort by start date, if desired). The task-specific view will show a `Stopped reason`.
