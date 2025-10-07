# Testnet Chart

The Testnet Chat is a Helm chart which can be used to deploy an instance of SourceHub, a relayer and create an IBC Connection between ShinzoHub and SourceHub.

# Requirements
- kubectl
- Helm installed locally
- Access to a kubernetes cluster (for local usage I recommend k3s which is a single binary and easy to use)
- An running instance of the [network-operator](https://github.com/sourcenetwork/network-operator/commits/main/)

# Usage

To create and remove instance of SourceHub, use the regular helm commands.

Example:
```sh
# assumes the current directory as working directory
helm install sourcehub . # install the chart at the current directory and call it "sourcehub"
helm uninstall sourcehub # uninstall the chart named sourcehub
```

To check the status of SourceHub, use normal kubernetes commands such as `kubectl get pods`, `kubectl describe pods {pod-name}` and so on.

The network operator add some custom resource definitions which are part of the api. 
These resources are called `network`, `validator`, `relayer`, `chaintx`, `ibcconnection`.
You can troubleshoot and inspect the deployment through these crds.

The default network id for the SourceHub deployment is `sourcehub-devnet`.

Use `kubectl get pods -o wide` to see the IP of the SourceHub nodes and connect to them.