
---
type: docs
weight: 1
menu:
  main:
    weight: 1
---

<!---
DO NOT EDIT. Generated by: "cd docs; npm run gen-docs"
-->

This repository documents a catalog of functions implementing [Configuration Functions Specification][spec].

These functions can be implemented using any toolchain such as the [KPT Functions SDK][sdk].

## Sources

See [definition of source functions][source].

| Image                          | Args              | Description                                                       | Source                                                                                                           |
| ------------------------------ | ----------------- | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| gcr.io/kpt-dev/kpt             | fn source         | Reads a directory of Kubernetes configuration recursively.        | [Link](https://github.com/kubernetes-sigs/kustomize/blob/master/cmd/config/internal/commands/source.go)          |
| gcr.io/kpt-functions/read-yaml |                   | [Demo] Reads a directory of Kubernetes configuration recursively. | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/read_yaml.ts) |
| gcr.io/cloud-builders/kubectl  | get [...] -o yaml | Get one or many resources from a Kubernetes cluster.              | [Link](https://github.com/GoogleCloudPlatform/cloud-builders/blob/master/kubectl/Dockerfile)                     |

## Sinks

See [definition of sink functions][sink].

| Image                           | Args    | Description                                                                                                                       | Source                                                                                                            |
| ------------------------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| gcr.io/kpt-dev/kpt              | fn sink | Writes a directory of Kubernetes configuration. It maintains the original directory structure as read by source functions.        | [Link](https://github.com/kubernetes-sigs/kustomize/blob/master/cmd/config/internal/commands/sink.go)             |
| gcr.io/kpt-functions/write-yaml |         | [Demo] Writes a directory of Kubernetes configuration. It maintains the original directory structure as read by source functions. | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/write_yaml.ts) |

## Validators

| Image                                     | Args | Description                                                                                                      | Source                                                                                                                      |
| ----------------------------------------- | ---- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| gcr.io/kpt-functions/gatekeeper-validate  |      | Enforces OPA constraints on input objects. The constraints are also passed as part of the input to the function. | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/go/pkg/functions/gatekeeper/validate.go)       |
| gcr.io/kpt-functions/validate-rolebinding |      | [Demo] Enforces a blacklist of subjects in RoleBinding objects.                                                  | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/validate_rolebinding.ts) |

## Generators

| Image                               | Args | Description                                                                                          | Source                                                                                                                |
| ----------------------------------- | ---- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| gcr.io/kpt-functions/expand-team-cr |      | [Demo] Reads custom resources of type Team and generates multiple Namespace and RoleBinding objects. | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/expand_team_cr.ts) |

## Transformers

| Image                                | Args | Description                                                                                 | Source                                                                                                              |
| ------------------------------------ | ---- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| gcr.io/kpt-functions/mutate-psp      |      | [Demo] Mutates PodSecurityPolicy objects by setting spec.allowPrivilegeEscalation to false. | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/mutate_psp.ts)   |
| gcr.io/kpt-functions/label-namespace |      | [Demo] Adds a label to all Namespaces.                                                      | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/hello-world/src/label_namespace.ts) |

## Miscellaneous

| Image                      | Args | Description                                | Source                                                                                                       |
| -------------------------- | ---- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| gcr.io/kpt-functions/no-op |      | [Demo] No Op function for testing purposes | [Link](https://github.com/GoogleContainerTools/kpt-functions-sdk/tree/master/ts/demo-functions/src/no_op.ts) |

[spec]: https://github.com/kubernetes-sigs/kustomize/blob/master/cmd/config/docs/api-conventions/functions-spec.md
[source]: https://googlecontainertools.github.io/kpt-functions-sdk/docs/concepts.html#source-function
[sink]: https://googlecontainertools.github.io/kpt-functions-sdk/docs/concepts.html#sink-function
[sdk]: https://googlecontainertools.github.io/kpt-functions-sdk/
