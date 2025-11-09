# Configuration for []()

Project is structured as:

```yml
.
├── argocd
│   └── applications
│       ├── staging.yaml
│       └── production.yaml
├── manifest
│   ├── base
│   ├── ...resources .yml files
│   └── kustomization.yml
└── overlays
    ├── production
    │   ├── BackupTodoCronJob.yml
    │   └── kustomization.yml
    └── staging
        └── kustomization.yml
```

Whenever a change is made, cluster is updated by the ArgoCD.
There is also a workflow that is triggered whenever a changed is made in the [project server repo](https://github.com/andreasZel/devops_with_kubernetes_project_server), to also commit changes in the `overlays kustomization`.