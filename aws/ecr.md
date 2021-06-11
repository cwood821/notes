# Elastic Container Registry (ECR)

The structure of ECR is `Registry -> Repository -> Image -> Tag`

## List repositories in registry

```
aws ecr describe-repositories
```


## List images in a repository

```
aws ecr describe-images --repository-name my-repo
```

This output will list images, including their tags.