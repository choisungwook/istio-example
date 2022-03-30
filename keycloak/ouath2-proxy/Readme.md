# 개요
* oauth2-proxy 설정

# 준비
* keyclaok이 이미 설치되어 있어야 함

# 설치
* namespace 생성
```sh
kubectl create ns oauth2-proxy
```

* secret 수정 후 배포
  * keycloak real, realm의 secret 설정
```sh
kubectl apply -f secret.yaml
```

* deployment 수정 후 배포
  * keycloak service domain설정
  * keyckaok realm 설정
  * whitelist-domaind 수정

![](imgs/kyecloak-svc.png)

![](imgs/keycloak-realm.png)

```sh
kubectl apply -f deployment.yaml
```

* service 배포
```sh
kubectl apply -f service.yaml
```

# 참고자료
* https://www.cnblogs.com/gxc888/p/15894466.html
* https://zenn.dev/takitake/articles/a91ea116cabe3c