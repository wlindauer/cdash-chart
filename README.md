# CDash Helm Chart
Helm chart for deploying a [CDash](https://cdash.org) testing server to Kubernetes.

## Introduction
[CDash](https://cdash.org) is an open source, web-based software testing server. CDash aggregates, analyzes and displays the results of software testing processes submitted from clients located around the world. Developers depend on CDash to convey the state of a software system, and to continually improve its quality.

CDash is a part of a larger software process that integrates [Kitware’s](https://www.kitware.com/platforms/#cmake) [CMake](https://cmake.org), CTest, and CPack tools.

## Installation
### Prerequisites
The CDash chart requires [Helm v3](https://helm.sh). You can install Helm using package managers like
```
brew install helm
sudo snap install helm --classic
```
If you are still using Helm v2, you will need to [migrate](https://helm.sh/docs/topics/v2_v3_migration/) first.

### Setup
Once you have Helm ready, you can add the chart repository.
```
helm repo add cdash https://wlindauer.github.io/cdash-chart
```

### Install
To install using default values
```
helm install cdash cdash/cdash
```
If you are using minikube you might want to override the service type to `NodePort`.
```
helm install cdash cdash/cdash --set service.type=NodePort
```
To see the availiable values that are configurable and their defaults
```
helm show values cdash/cdash
```

### Uninstall
To remove the release and chart repository
```
helm delete cdash
helm repo remove cdash
```
