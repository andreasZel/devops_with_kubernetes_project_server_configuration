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

Whenever a change is made, images are being updated in the overlay kustomization and 
are being detected by the ArgoCD in the cluster.