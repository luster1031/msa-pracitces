# MSA
+ servers, services를 잘 구성해야함
+ 하나의 서비스 클라우드라고 생각해라
    + 하나의 레지스트리 기반으로 
1. servers/service-registry-server
    + 유레카 서버 설정
    ```yml
    eureka:
        instance:
            hostname: localhost
        server:
            enableSelfPreservation: false
            waitTimeInMsWhenSyncEmpty: 5        
        client:
            fetchRegistry: false
            registerWithEureka: false
            serviceUrl:
                defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka
    ```
    + defaultZone : registry 서버
        + zone기준으로 물어봐야함
         