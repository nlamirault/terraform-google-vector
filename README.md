# Vector into Google Cloud Platform

![Tfsec](https://github.com/nlamirault/terraform-google-vector/workflows/Tfsec/badge.svg)

## Usage

```hcl
module "vector" {
  source  = "nlamirault/vector/google"
  version = "1.0.0"

  project = var.project

  bucket_location      = var.bucket_location
  bucket_storage_class = var.bucket_storage_class
  bucket_labels        = var.bucket_labels

  namespace       = var.namespace
  service_account = var.service_account

  keyring_location = var.keyring_location
}
```

and variables :

```hcl
project = "foo-prod"

region = "europe-west1"

##############################################################################
# vector

bucket_location      = "europe-west1"
bucket_storage_class = "STANDARD"
bucket_labels        = {
  env      = "prod"
  service  = "vector"
  made-by  = "terraform"
}

namespace       = "storage"
service_account = "vector"

keyring_location = "europe-west1"
```

## Documentation

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.14.0 |
| google | >= 3.54.0 |

## Providers

| Name | Version |
|------|---------|
| google | >= 3.54.0 |

## Modules

No Modules.

## Resources

| Name |
|------|
| [google_kms_crypto_key](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/kms_crypto_key) |
| [google_kms_crypto_key_iam_binding](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/kms_crypto_key_iam_binding) |
| [google_kms_key_ring](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/kms_key_ring) |
| [google_service_account](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/service_account) |
| [google_service_account_iam_member](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/service_account_iam_member) |
| [google_storage_bucket](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/storage_bucket) |
| [google_storage_bucket_iam_member](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/resources/storage_bucket_iam_member) |
| [google_storage_project_service_account](https://registry.terraform.io/providers/hashicorp/google/3.54.0/docs/data-sources/storage_project_service_account) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| bucket\_labels | Map of labels to apply to the bucket | `map(string)` | <pre>{<br>  "made-by": "terraform"<br>}</pre> | no |
| bucket\_location | The bucket location | `string` | n/a | yes |
| bucket\_storage\_class | Bucket storage class. | `string` | `"MULTI_REGIONAL"` | no |
| keyring\_location | The KMS keyring location | `string` | n/a | yes |
| namespace | The Kubernetes namespace | `string` | n/a | yes |
| project | The project in which the resource belongs | `string` | n/a | yes |
| service\_account | The Kubernetes service account | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| service\_account | Service Account for vector |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
