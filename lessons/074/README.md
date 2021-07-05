# Vertical Pod Autoscaling

[YouTube Tutorial]()

## 1. Create EKS Cluster Using eksctl
```bash
eksctl create cluster -f eks.yaml
```

## 2. Deploy Metrics server (YAML)

- Create deployemnt files under `0-metrics-server` directory
  - `0-service-account.yaml`
  - `1-cluster-roles.yaml`
  - `2-role-binding.yaml`
  - `3-cluster-role-bindings.yaml`
  - `4-service.yaml`
  - `5-deployment.yaml`
  - `6-api-service.yaml`

$ helm repo add bitnami https://charts.bitnami.com/bitnami
$ helm install my-release bitnami/metrics-server
https://github.com/bitnami/charts/tree/master/bitnami/metrics-server

## 3. Deploy Metrics server (HELM)

## 3. Install Vertical Pod Autoscaler

## 4. Upgrade LibreSSL on Mac/OS X

## 5. Install Vertical Pod Autoscaler (Continue)

## 6. Demo

## 7. Conclusion

- Clone VPA repo
```
git clone https://github.com/kubernetes/autoscaler.git
```
- Change directory
```
cd autoscaler/vertical-pod-autoscaler
```
- Preview installation
```
./hack/vpa-process-yamls.sh print
```
- Install VPA
```
./hack/vpa-up.sh
```

- Get error
- Get verion of openssl
- Explain the openssl is an alias for libressl
- Upgrade LibreSSL on mac
- Explain why LibreSSL is better
```
openssl version
```
```
which openssl
```

```
➜  vertical-pod-autoscaler git:(master) which openssl
/usr/bin/openssl
➜  vertical-pod-autoscaler git:(master) openssl version -a
LibreSSL 2.8.3
built on: date not available
platform: information not available
options:  bn(64,64) rc4(ptr,int) des(idx,cisc,16,int) blowfish(idx)
compiler: information not available
OPENSSLDIR: "/private/etc/ssl"
```

```
brew info openssl
brew info libressl
brew install libressl
/opt/homebrew/opt/libressl/bin/openssl version
openssl version
which openssl
sudo mv /usr/bin/openssl /usr/bin/openssl-default
sudo ln -s /opt/homebrew/opt/libressl/bin/openssl /usr/bin/openssl



sudo ln -s /opt/homebrew/opt/libressl/bin/openssl /usr/local/bin/openssl

(/usr/local/opt/libressl/bin/openssl)
openssl version
open new tab
brew remove libressl

But this is known to cause problems with some more recent versions of OSX. Better to just insert a new symlink into /usr/local/bin, which should take precedence on your path over /usr/bin.
```

watch kubectl top pods
kubectl describe vpa hamster-vpa


in intro tell that at the end I'll explain how I use it in productuion

## Clean Up
- Delete EKS cluster
```
eksctl delete cluster -f eks.yaml
sudo rm /usr/local/bin/openssl
brew remove libressl
```
