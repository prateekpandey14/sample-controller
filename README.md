# sample-controller

This repository implements a simple controller for watching Foo resources as
defined with a CustomResourceDefinition (CRD).

This particular example demonstrates how to perform basic operations such as:

* How to register a new custom resource (custom resource type) of type `Foo` using a CustomResourceDefinition.
* How to create/get/list instances of your new resource type `Foo`.
* How to setup a controller on resource handling create/update/delete events.

It makes use of the generators in [k8s.io/code-generator](https://github.com/kubernetes/code-generator)
to generate a typed client, informers, listers and deep-copy functions. You can
do this yourself using the `./hack/update-generated-crd-code.sh` script.

The `update-generated-crd-code.sh` script will automatically generate the following files &
directories:

* `pkg/apis/maya/v1alpha1/zz_generated.deepcopy.go`
* `pkg/client/`
* `pkg/generated`

Changes should not be made to these files manually, and when creating your own
controller based off of this implementation you should not copy these files and
instead run the `hack/update-generated-crd-code.sh` script to generate your own.

### Dependency Management :
Dep used as dependency management tool.
