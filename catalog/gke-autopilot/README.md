<!-- BEGINNING OF PRE-COMMIT-BLUEPRINT DOCS HOOK:TITLE -->
# GKE Autopilot blueprint


<!-- END OF PRE-COMMIT-BLUEPRINT DOCS HOOK:TITLE -->
<!-- BEGINNING OF PRE-COMMIT-BLUEPRINT DOCS HOOK:BODY -->
A blueprint to create a GKE Autopilot cluster. An existing subnet needs to be provided where the cluster should be created.

## Setters

|        Name         |                             Value                              | Type | Count |
|---------------------|----------------------------------------------------------------|------|-------|
| cluster-name        | example-us-west4                                               | str  |     2 |
| location            | us-east4                                                       | str  |     1 |
| master-ip-range     | 10.254.0.0/28                                                  | str  |     1 |
| network-ref         | projects/network-project-id/global/networks/default            | str  |     1 |
| platform-namespace  | config-control                                                 | str  |     1 |
| pods-range-name     | pods                                                           | str  |     1 |
| project-id          | project-id                                                     | str  |     4 |
| projects-namespace  | projects                                                       | str  |     1 |
| services-range-name | services                                                       | str  |     1 |
| subnet-ref          | projects/network-project-id/regions/region/subnetworks/default | str  |     1 |

## Sub-packages

- [gke-cluster](cluster)

## Resources

This package has no top-level resources. See sub-packages.

## Resource References

This package has no top-level resources. See sub-packages.

## Usage

1.  Clone the package:
    ```shell
    kpt pkg get https://github.com/GoogleCloudPlatform/blueprints.git/catalog/gke-autopilot@${VERSION}
    ```
    Replace `${VERSION}` with the desired repo branch or tag
    (for example, `main`).

1.  Move into the local package:
    ```shell
    cd "./gke-autopilot/"
    ```

1.  Edit the function config file(s):
    - setters.yaml

1.  Execute the function pipeline
    ```shell
    kpt fn render
    ```

1.  Initialize the resource inventory
    ```shell
    kpt live init --namespace ${NAMESPACE}"
    ```
    Replace `${NAMESPACE}` with the namespace in which to manage
    the inventory ResourceGroup (for example, `config-control`).

1.  Apply the package resources to your cluster
    ```shell
    kpt live apply
    ```

1.  Wait for the resources to be ready
    ```shell
    kpt live status --output table --poll-until current
    ```

<!-- END OF PRE-COMMIT-BLUEPRINT DOCS HOOK:BODY -->
