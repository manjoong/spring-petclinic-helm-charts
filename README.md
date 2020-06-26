# 실행 조건:
1. k8s cluster구성
2. helm 2.x, 3.x 설치
3. tiller deployment 구성 및 권한 확인
4. nginx-controller 구성
5. pv 사용 가능한 storage-class 구성
6. default namespace 확인 


# 실행 방법




● gradle​을 사용하여 어플리케이션과 도커이미지를 빌드한다.​
● 어플리케이션의 ​log​는 ​host​의 ​/logs ​디렉토리에 적재되도록 한다​.
● 정상 동작 여부를 반환하는 ​api​를 구현하며​, 10​초에 한번 체크하도록 한다​. 3​번 연속
체크에 실패하 면 어플리케이션은 ​restart ​된다​.
● 종료 시 ​30​초 이내에 프로세스가 종료되지 않으면 ​SIGKILL​로 강제 종료 시킨다​.
● 배포 시와 ​scale in/out ​시 유실되는 트래픽이 없어야 한다​.
● 어플리케이션 프로세스는 ​root ​계정이 아닌 ​uid:1000​으로 실행한다​.
● DB​도 ​kubernetes​에서 실행하며 재 실행 시에도 변경된 데이터는 유실되지 않도록
설정한다​. ​어플리케이션과 ​DB​는 ​cluster domain​을 이용하여 통신한다​.
● nginx-ingress-controller​를 통해 어플리케이션에 접속이 가능하다​.
● namespace​는 ​default​를 사용한다​.
● README.md ​파일에 실행 방법을 기술한다​.
