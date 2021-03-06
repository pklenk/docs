---

copyright:
  years: 2015, 2016

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 외부 서비스 통합
{: #ref-index}
마지막 업데이트 날짜: 2016년 9월 26일
{: .last-updated}

외부 서비스 통합을 사용하면 {{site.data.keyword.iot_full}} 조직에 있는 써드파티 또는 외부 서비스의 오퍼레이션과 데이터에 액세스할 수 있습니다.

## Jasper
{: #jasper}

Jasper는 SIM 디바이스의 관리 플랫폼입니다. Jasper는 {{site.data.keyword.iot_short_notm}} 대시보드에 통합되므로 {{site.data.keyword.iot_short_notm}} 조직 대시보드를 통해 Jasper 디바이스를 관리할 수 있습니다.

### Jasper에 지원되는 오퍼레이션

IBM 플랫폼을 통해 제공되는 기본 제공 Jasper 통합에서는 다음과 같은 Jasper 오퍼레이션을 지원합니다.

- 전체 Jasper 데이터 보기
  - 상태, 요금제, 월별 데이터 사용, 월별 SMS 사용, 월별 음성 사용, 초과 한도, 추가된 날짜 및 수정한 날짜를 표시합니다.
- SIM 활성화 상태 변경
  - 인벤토리, 활성화 준비, 활성화됨, 비활성화됨 및 폐기됨 중에 선택하십시오.
- SIM 사용 보기
  - 주기 시작 날짜, 청구 가능 및 총 데이터, 청구 가능 및 총 SMS, 청구 가능 및 총 음성을 표시합니다.
  - 주기 시작 날짜는 YYYY-MM-DD 형식을 사용하여 설정할 수 있습니다.
- SIM에 SMS 전송
- 요금제 변경

다음 구성 단계가 완료된 후 Jasper에 연결된 디바이스의 디바이스 드릴 다운에서 지원되는 오퍼레이션에 액세스할 수 있습니다.


### Jasper 구성

{{site.data.keyword.iot_short_notm}} 조직에 Jasper 서비스를 연결하려면 먼저 두 단계의 구성을 수행해야 합니다. 먼저 {{site.data.keyword.iot_short_notm}}을 Jasper 서비스에 연결한 다음 {{site.data.keyword.iot_short_notm}} 디바이스를 구성해야 합니다.


1. Jasper 확장기능을 사용하십시오. {{site.data.keyword.iot_short_notm}} 조직과 Jasper를 통합할 수 있으려면 다음 단계를 완료하십시오.
  1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **확장기능**을 선택하십시오.
  2. **확장기능** 페이지에서 **확장기능 추가**를 클릭하십시오.
  3. Jasper 옆의 **추가**를 클릭하십시오.
  4. Jasper 사용자 이름, 비밀번호, 액세스 키 및 도메인 ID를 입력하십시오.
  5. **완료**를 클릭하십시오.

2. 디바이스를 구성하십시오.
{{site.data.keyword.iot_short_notm}} 대시보드에서 Jasper의 데이터를 표시하도록 {{site.data.keyword.iot_short_notm}} 조직과 Jasper 계정에 모두 연결된 디바이스를 구성할 수 있습니다.
**중요:** Jasper 구성은 디바이스 추가 프로세스의 일부로 적용할 수 없습니다. 이전에 연결된 디바이스만 Jasper로 구성할 수 있습니다.
Jasper 연결 디바이스를 구성하려면 다음 단계를 완료하십시오.
 1. {{site.data.keyword.iot_short_notm}} 대시보드의 디바이스 탭에서 구성할 Jasper 연결 디바이스를 찾으십시오.
 2. *디바이스 드릴 다운* 보기를 열 디바이스를 선택하십시오.
 3. *확장기능 구성*까지 아래로 화면이동하십시오.
 4. 다음 JSON 형식을 사용하여 확장기능 구성을 입력한 다음 **변경 확인**을 클릭하여 구성을 저장하십시오.  

```json  
    {
        "jasper": {
            "iccid": "string"
        }
    }

```

조직이 정상적으로 구성되면 *확장기능* 섹션이 *디바이스 드릴 다운* 보기의 *확장기능 구성* 섹션에 표시됩니다.

## AT&T
{: #att}

### AT&T에 지원되는 오퍼레이션

AT&T 확장기능을 사용하면 다음 AT&T 오퍼레이션을 수행할 수 있습니다.

- 전체 AT&T 데이터 보기
  - 상태, 요금제, 월별 데이터 사용, 월별 SMS 사용, 월별 음성 사용, 초과 한도, 추가된 날짜 및 수정한 날짜를 표시합니다.
- SIM 활성화 상태 변경
  - 인벤토리, 활성화 준비, 활성화됨, 비활성화됨 및 폐기됨 중에 선택하십시오.
- SIM 사용 보기
  - 주기 시작 날짜, 청구 가능 및 총 데이터, 청구 가능 및 총 SMS, 청구 가능 및 총 음성을 표시합니다.
  - 주기 시작 날짜는 YYYY-MM-DD 형식을 사용하여 설정할 수 있습니다.
- SIM에 SMS 전송
- 요금제 변경

### AT&T의 구성

{{site.data.keyword.iot_short_notm}} 조직을 AT&T에 연결하려면 조직 구성 및 디바이스 구성을 완료해야 합니다.

{{site.data.keyword.iot_short_notm}} 플랫폼을 구성하려면 다음 단계를 완료하십시오.

1. AT&T 확장 기능을 사용하십시오. AT&T와 {{site.data.keyword.iot_short_notm}} 조직을 통합할 수 있으려면 다음 단계를 완료하십시오.
  1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **확장기능**을 선택하십시오.
  2. **확장기능** 페이지에서 **확장기능 추가**를 클릭하십시오.
  3. AT&T 옆의 **추가**를 클릭하십시오.
  4. AT&T 사용자 이름, 비밀번호, 액세스 키 및 도메인 ID를 입력하십시오.
  5. **완료**를 클릭하십시오.

{{site.data.keyword.iot_short_notm}} 조직을 AT&T 계정과 연결하려면 먼저 두 단계의 구성을 수행해야 합니다. 조직 구성을 완료한 다음 디바이스를 구성하십시오.


2. 디바이스를 구성하십시오.
{{site.data.keyword.iot_short_notm}} 대시보드에서 AT&T의 데이터를 표시하도록 {{site.data.keyword.iot_short_notm}} 조직과 AT&T 계정에 모두 연결된 디바이스를 구성할 수 있습니다.
**중요:** AT&T 구성은 디바이스 추가 프로세스의 일부로 적용할 수 없습니다. 이전에 연결된 디바이스만 AT&T로 구성할 수 있습니다.
AT&T 연결 디바이스를 구성하려면 다음 단계를 완료하십시오.
 1. {{site.data.keyword.iot_short_notm}} 대시보드의 디바이스 탭에서 구성할 AT&T 연결 디바이스를 찾으십시오.
 2. *디바이스 드릴 다운* 보기를 열 디바이스를 선택하십시오.
 3. *확장기능 구성*까지 아래로 화면이동하십시오.
 4. 다음 JSON 형식을 사용하여 확장기능 구성을 입력한 다음 **변경 확인**을 클릭하여 구성을 저장하십시오.  

```json
    {
        "atnt": {
            "iccid": "string"
        }
    }

```

조직이 정상적으로 구성되면 *확장기능* 섹션이 *디바이스 드릴 다운* 보기의 *확장기능 구성* 섹션에 표시됩니다.


## ARM mbed 커넥터
{: #arm}

ARM mbed 커넥터를 사용하면 {{site.data.keyword.iot_short_notm}}에 ARM mbed 디바이스를 연결할 수 있습니다. ARM mbed 확장기능에서는 ARM mbed 포털이 허용되며 {{site.data.keyword.iot_short_notm}}이 ARM mbed 포털에서 데이터를 송수신할 수 있습니다.

### 구성 설정


1. ARM mbed 커넥터 확장기능을 사용하십시오. ARM mbed 커넥터 확장기능을 사용으로 설정하려면 다음 단계를 완료하십시오.
  1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **설정**을 선택하고 **확장기능**으로 이동하십시오.
  2. **확장기능** 메뉴에서 **확장기능 추가**를 클릭하십시오.
  3. ARM mbed 커넥터 확장기능 옆의 **추가**를 클릭하십시오.
  4. ARM mbed 액세스 키 및 도메인 ID를 입력하십시오. 이 키와 ID는 https://connector.mbed.com에서 ARM mbed 포털을 사용하여 찾을 수 있습니다.
  5. **연결 확인** 단추를 클릭하여 신임 정보가 올바른지 확인하십시오.
  6. **완료**를 클릭하십시오.

### 페이로드 형식

ARM mbed 플랫폼, 알림 및 비동기 응답에서 수신되는 두 가지 유형의 메시지가 있습니다. {{site.data.keyword.iot_short_notm}}은 ARM mbed 플랫폼에 연결된 디바이스로 명령을 보낼 수 있습니다.

#### 알림

디바이스 또는 센서 데이터의 변경사항에 의해 알림이 생성됩니다. {{site.data.keyword.iot_short_notm}}은 메시지를 처리한 후 {{site.data.keyword.iot_short_notm}}에 디바이스를 직접 연결한 것과 같은 방식으로 디바이스 이벤트 주제에 공개합니다. ARM mbed 플랫폼에 연결된 디바이스에서 시작된 알림에 사용되는 이벤트 유형은 `notify`입니다.

다음 코드 샘플은 ARM mbed 플랫폼 API에서 보낸 알림에 대한 페이로드 형식을 표시합니다.

```
{
  "ep":<endpoint/deviceID>,
  "path":<resource path>,
  "ct":<content type>,
  "payload":<Base64 encoded payload>,
  "max-age":<how long the payload is valid, in seconds>
}
```

#### 비동기 응답

{{site.data.keyword.iot_short_notm}}이 ARM mbed 플랫폼에 연결된 디바이스로 명령을 보내면 디바이스가 {{site.data.keyword.iot_short_notm}}으로 다시 확인 메시지를 보냅니다. 이 확인 메시지는 *비동기 응답*이라고 하며 이벤트 유형 `asyncResponse`를 사용합니다.

다음 코드 샘플은 ARM mbed 클라우드 서비스에서 보낸 비동기 응답에 대한 페이로드 형식을 표시합니다.

```
{
  "id":<transaction id>,
  "status":<200 is command was sucessfully executed. Check other HTTP response codes>,
  "ct":<content type>,
  "max-age":<how long the payload is valid, in seconds>,
  "payload":<base64 encoded payload>,
  "ep":<endpoint/deviceID affected by the command>,
  "path":<resource path affected by the command>
}
```

#### ARM mbed 플랫폼으로 명령 보내기

{{site.data.keyword.iot_short_notm}}은 ARM mbed 플랫폼에 연결된 디바이스로 명령을 보낼 수 있습니다. ARM mbed 플랫폼으로 보낸 명령은 다음 JSON 형식을 사용해야 합니다.

```
{
  "method":<PUT or POST>,
  "deviceId":<endpoint/deviceId>,
  "resourceId":<resource path>,
  "payload": <Base64 encoded payload>
}
```
선택한 메소드는 대소문자를 구분합니다. 자원 경로의 처음 '/'는 건너뛰어야 합니다.


다음 주제에 페이로드를 공개해야 합니다.

```
iot-2/type/<device_type>/id/<deviceId>/cmd/<command_type>/fmt/<command_format>
```


## Orange
{: #orange}

Orange 확장기능을 사용하면 {{site.data.keyword.iot_short_notm}}에 연결되었으며 Orange SIM 카드가 설치된 디바이스에서 SIM 카드 데이터를 볼 수 있습니다.

https://developer.ibm.com/iotplatform/2016/03/30/watson-iot-platform-integration-with-orange-beta/

### Orange에 지원되는 오퍼레이션

{{site.data.keyword.iot_short_notm}} 서비스에 연결되어 있고 Orange SIM 카드가 있는 디바이스가 있으면 Orange 확장기능을 사용하여 다음 SIM 카드 데이터를 볼 수 있습니다.

- SIM 일련 번호
- 활성화 상태
- 마지막 상태 변경
- 마지막 상태 새로 고치기
- 위치 상태

### Orange 구성



Orange 확장기능을 사용하려면 다음을 수행하십시오.

1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **확장기능**을 선택하십시오.
2. **확장기능** 페이지에서 **확장기능 추가**를 클릭하십시오.
3. Orange 확장기능 옆의 **추가**를 클릭하십시오.
4. Orange 사용자 이름과 비밀번호를 입력하십시오.
6. **완료**를 클릭하십시오.

Orange 확장기능을 사용으로 설정하고 나면 Orange SIM 데이터를 표시하도록 Orange SIM 카드가 있는 각 디바이스를 구성해야 합니다.

1. {{site.data.keyword.iot_short_notm}} 대시보드의 디바이스 탭에서 구성할 Orange SIM 디바이스를 찾으십시오.
2. 디바이스를 선택하고 *확장기능 구성*까지 아래로 화면이동하십시오.
3. 다음 JSON 형식을 사용하여 확장기능 구성을 입력한 다음 **변경 확인**을 클릭하여 구성을 저장하십시오.

```  
    {
        "orange": {
            "serialnumber": "<serial number of Orange SIM>"
        }
    }

```
조직이 정상적으로 구성되면 *확장기능* 섹션이 *디바이스 드릴 다운* 보기의 *확장기능 구성* 섹션에 표시됩니다.


## 히스토리 데이터 스토리지
{: #historical_data}

히스토리 데이터 스토리지 확장기능을 사용하면 IoT 데이터에 대해 호환 가능한 메시지 스토리지 서비스(예: [{{site.data.keyword.cloudantfull}}](../../cloudant_connector.html) 또는 [{{site.data.keyword.messagehub_full}}](../../message_hub.html))를 찾아 구성할 수 있습니다.

## 사용자 정의 디바이스 관리 패키지
{: #device_mgmt}

디바이스 관리는 {{site.data.keyword.iot_short_notm}}의 코어 기능이지만 추가 기능을 개발하기 위해 확장할 수 있습니다.

디바이스 관리 확장기능을 사용하면 디바이스 관리용 사용자 정의 기능을 설치할 수 있습니다. 사용자 정의 디바이스 관리 기능에 대한 자세한 정보는 [디바이스 관리 사용자 정의 확장기능](../../devices/device_mgmt/custom_actions.html){: new_window}을 참조하십시오.

## 블록체인(Blockchain)
{: #blockchain}

블록체인이 포함된 {{site.data.keyword.iot_short_notm}}을 사용하면 IoT 디바이스에서 블록체인 트랜잭션에 데이터를 제공할 수 있으므로, 블록체인의 불변 원장에 데이터를 저장하고 스마트 계약 비즈니스 규칙에서 사용할 수 있습니다. {{site.data.keyword.iot_short_notm}}에서 블록체인의 스마트 계약에 필요한 데이터 형식에 디바이스 데이터를 맵핑한 다음 블록체인 원장에 저장하도록 블록체인 패브릭에 전달합니다.

### 블록체인에 지원되는 오퍼레이션
- 스마트 계약을 디바이스 이벤트로 업데이트하도록 트리거합니다.
- 스마트 계약 비즈니스 로직을 실행하여 원장 상태를 디바이스 이벤트 데이터로 업데이트합니다.
- 모니터링 UI로 블록체인, 트랜잭션 및 원장 상태를 모니터합니다.

### 블록체인 구성

{{site.data.keyword.iot_short_notm}} 블록체인 통합은 {{site.data.keyword.iot_short_notm}}에서 기본적으로 활성화되지 않는 서비스 오퍼링입니다. 사용자 환경에서 이 기능을 활성화하려면 다음 단계를 완료하십시오.
 1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **확장기능**을 클릭하십시오.
 2. 블록체인 확장기능 옆의 **자세한 정보** 링크를 클릭하여 IoT 블록체인 서비스 오퍼링 페이지로 이동하십시오.
 3. 서비스 요청 양식을 작성하여 제출하십시오.
일반적으로 서비스를 승인하는 데는 하루 정도 걸립니다. 요청이 승인되고 나면 {{site.data.keyword.iot_short_notm}} 조직에서 블록체인 통합을 활성화하는 방법에 대한 지시사항이 포함된 이메일이 전송됩니다.
 5. 조직이 설정을 완료하도록 {{site.data.keyword.iot_short_notm}} 대시보드로 돌아가십시오. 자세한 정보는 [{{site.data.keyword.iot_short_notm}} 블록체인 통합](../../bl_blockchain_integration.html)을 참조하십시오.

## Weather Company
{: #weathercompany}

Weather Company 확장기능은 기존 {{site.data.keyword.iot_short_notm}} 디바이스와 날씨 데이터를 결합합니다. API를 사용하여 업데이트 위치 요청이 작성되었거나 디바이스 관리 메시지를 사용하여 디바이스가 이미 해당 위치를 설정한 경우 Weather Company의 날씨 데이터가 디바이스 세부사항 보기에 표시됩니다.

**참고:** 관리 디바이스만 고유 위치를 설정할 수 있습니다. 모든 비관리 디바이스에 API를 사용하여 수동으로 설정된 위치가 있어야 합니다. 디바이스 위치 설정에 대한 자세한 정보는 [위치 찾기 요청](../../devices/device_mgmt/index.html#update-location)을 참조하십시오.

### 날씨 데이터

디바이스 위치에 대해 검색된 날씨 데이터를 보려면 **디바이스** 분할창에서 디바이스를 찾고 이를 클릭하십시오. 상세 디바이스 보기에서 **확장기능** 섹션까지 아래로 화면이동하십시오. 다음 날씨 데이터가 나열됩니다.

- 현재 날씨.
- 현재 온도.
- 예상된 최대 및 최저 온도.
- 상대 습도.
- 기압.
- 가시성.
- 풍속.
- 풍향.
- 위도.
- 경고.

<!-- Weather data from The Weather Company extension can be retrieved by using the API. For information on the Weather Company API, see [The Weather Company API documentation](https://docs.internetofthings.ibmcloud.com/swagger/ext-twc.html). -->
