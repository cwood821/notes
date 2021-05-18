# Cloudformation Updates

[CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-whatis-howdoesitwork.html) creates a `stack` of resources on AWS based on a provided template.

You can update an existing stack, but this may cause service interruption.

Depending on changes, [updates could behave differently](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html): no interruption, some interruption, or replacement.

For replacement, according to documentation: 
> AWS CloudFormation recreates the resource during an update, which also generates a new physical ID. AWS CloudFormation usually creates the replacement resource first, changes references from other dependent resources to point to the replacement resource, and then deletes the old resource.

See the [AWS REsource Types Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html) to see the effects of updating particular resource properties.

### ECS Services

When updating an ECS service, interruption may depend on the [deployment configuration](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/update-service.html).

See [ECS note](ecs.md).

