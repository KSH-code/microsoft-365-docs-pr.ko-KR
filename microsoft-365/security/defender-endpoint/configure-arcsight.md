---
title: 엔드포인트 감지를 위해 Microsoft Defender를 끌어오도록 마이크로 포커스 ArcSight 구성
description: 마이크로 포커스 ArcSight를 구성하여 검색된 정보를 수신하고 끌어오도록 Microsoft Defender 보안 센터
keywords: Micro Focus ArcSight 구성, 보안 정보 및 이벤트 관리 도구, arcsight 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1ab7e1f31fff1e4b553d5d301eb7fbe4749de19e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185915"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>엔드포인트 감지를 위해 Defender를 끌어오도록 마이크로 포커스 ArcSight 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configurearcsight-abovefoldlink)

일부 파일 및 도구를 설치하고 구성하여 마이크로 포커스 ArcSight를 사용하여 끝점 감지를 위해 Defender를 끌어와야 합니다.

> [!NOTE]
>
> - [Endpoint용 Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.
> - [Endpoint 검색용 Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.

## <a name="before-you-begin"></a>시작하기 전에

Micro Focus ArcSight 커넥터 도구를 구성하려면 AAD(Micro Focus ArcSight Connector) 응용 프로그램에서 검색을 끌어 Azure Active Directory 구성 파일이 필요합니다.

이 섹션에서는 필요한 구성 파일을 올바르게 설정하고 사용하는 데 필요한 정보를 안내합니다.

- 사용자 설정 메뉴에서 SIEM 통합 기능을 사용하도록 **설정해야 설정** 합니다. 자세한 내용은 [Endpoint용 Defender에서 SIEM 통합 사용 을 참조하세요.](enable-siem-integration.md)

- SIEM 통합 기능을 사용하도록 설정하여 저장한 파일을 준비합니다. 다음 값을 얻게 됩니다.
  - OAuth 2.0 토큰 새로 고침 URL
  - OAuth 2.0 클라이언트 ID
  - OAuth 2.0 클라이언트 비밀

- 다음 구성 파일을 준비합니다.
- 
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    조직에서 사용하는 SIEM .zip 마이크로 포커스 ArcSight를 선택한 경우 이러한 두 파일이 포함된 파일 형식을 저장한 것입니다.

- 다음 토큰을 생성하고 준비해야 합니다.
  - 액세스 토큰
  - 새로 고침 토큰

  포털의 **SIEM** 통합 설정 섹션에서 이러한 토큰을 생성할 수 있습니다.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>마이크로 포커스 ArcSight FlexConnector 설치 및 구성

다음 단계에서는 시작하기 전에의 모든 필수 단계를 [완료했다고 가정합니다.](#before-you-begin)

1. FlexConnector 설치 Windows 최신 32비트 버전을 설치합니다. HPE 소프트웨어 센터에서 찾을 수 있습니다. 이 도구는 일반적으로 다음과 같은 기본 위치에 `C:\Program Files\ArcSightFlexConnectors\current\bin` 설치됩니다. .</br></br>C: \current\bin과 같은 도구를 저장할 위치를 선택할 수 \\ *있습니다folder_location*\current\bin은 folder_location 위치를 나타내는 위치입니다. 

2. 다음 작업을 수행하여 설치 마법사를 수행합니다.
   - 소개
   - 폴더 설치 선택
   - 설치 집합 선택
   - 바로 가기 폴더 선택
   - 사전 설치 요약
   - 설치 중...

   이러한 각 작업에 대한 기본값을 유지하거나 요구 사항에 맞게 선택을 수정할 수 있습니다.

3. 파일 탐색기를 열고 SIEM 통합 기능을 사용하도록 설정한 경우 저장한 두 구성 파일을 찾습니다. 두 파일을 FlexConnector 설치 위치에 저장합니다. 예를 들면 다음과 같습니다.

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\
   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 이 위치에 구성 파일을 넣어야 *합니다.* 여기서 folder_location 도구를 설치한 위치를 나타내야 합니다.

4. 핵심 커넥터 설치가 완료되면 커넥터 설치 창이 열립니다. 커넥터 설정 창에서 **커넥터 추가를 선택합니다.**

5. 유형: **ArcSight FlexConnector REST를 선택하고** 다음을 **클릭합니다.**

6. 매개 변수 세부 정보 양식에 다음 정보를 입력합니다. 양식의 다른 모든 값은 선택 사항이며 비워 두면 됩니다.

   <br>

   ****

   |필드|값|
   |---|---|
   |구성 파일|클라이언트 속성 파일의 이름을 입력합니다. 이름은 다운로드한 파일에서 제공한 .zip 일치해야 합니다. <p> 예를 들어 "flexagent" 디렉터리의 구성 파일의 이름이 "WDATP-Connector.jsonparser.properties"인 경우 클라이언트 속성 파일의 이름으로 "WDATP-Connector"를 입력해야 합니다.|
   |이벤트 URL|데이터 센터의 위치에 따라 EU 또는 미국 URL을 선택합니다. <ul><li>**EU의 경우**:  `https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**미국의 경우**: `https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**영국의** 경우 : `https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li></ul>|
   |인증 유형|OAuth 2|
   |OAuth 2 클라이언트 속성 파일|*wdatp-connector.properties* 파일의 위치로 이동하십시오. 이름은 다운로드한 파일에서 제공한 .zip 일치해야 합니다.|
   |새로 고침 토큰|**SIEM** 설정 페이지에서 새로 고침 토큰을 생성하거나 restutil 도구를 사용하여 두 가지 방법으로 새로 고침 토큰을 얻을 수 있습니다. <p> 기본 설정에서 새로 고침 토큰을 생성하는 데 대한 자세한 내용은 [Enable SIEM integration in Defender for Endpoint을 참조하세요.](enable-siem-integration.md)  <p> **restutil 도구를 사용하여 새로 고침 토큰을 얻다.** <ol><li>명령 프롬프트를 엽니다. C: \\ *폴더 \_ 위치*\current\bin으로 이동합니다. 여기서 폴더 위치는 도구를 설치한 위치를 나타내는 위치입니다. *\_*</li><li>Bin `arcsight restutil token -config` 디렉터리에서 입력합니다. 예: **arcsight restutil boxtoken -proxy proxy.location.hp.com:8080.** 웹 브라우저 창이 열립니다.</li><li>자격 증명을 입력한 다음 암호 필드를 클릭하여 페이지가 리디렉션될 수 있도록 합니다. 로그인 프롬프트에 자격 증명을 입력합니다.</li><li>새로 고침 토큰이 명령 프롬프트에 표시됩니다.</li><li>복사하여 새로 고침 토큰 **필드에 붙여 넣습니다.**|
   |

7. 브라우저 창이 커넥터에 의해 열립니다. 응용 프로그램 자격 증명으로 로그인합니다. 로그인한 후 OAuth2 클라이언트에 대한 권한을 부여할지 묻는 요청이 표시됩니다. 커넥터 구성이 인증될 수 있도록 OAuth 2 클라이언트에 대한 권한을 부여해야 합니다.

   https URL인 경우 로컬 호스트의 `redirect_uri` URL로 리디렉션됩니다. 로컬 호스트에서 실행되는 커넥터에서 제공한 인증서를 신뢰해야 하는 페이지가 표시됩니다. https가 https인 redirect_uri 인증서를 신뢰해야 합니다.

   그러나 웹 응용 redirect_uri URL을 지정하는 경우 인증서 신뢰에 동의할 필요가 없습니다.

8. 마이크로 포커스 ArcSight 커넥터 설정 창으로 돌아가서 커넥터 설정을 계속합니다.

9. **대상으로 ArcSight Manager(암호화)를** 선택하고 다음 을 **클릭합니다.**

10. 관리자 호스트 이름의 대상 IP/호스트 이름을 입력하고 매개 변수 양식에 자격 증명을 입력합니다.  양식의 다른 모든 값은 기본값으로 유지해야 합니다. **다음** 을 클릭합니다.

11. 커넥터 세부 정보 양식에 커넥터 이름을 입력합니다. 양식의 다른 모든 값은 선택 사항이며 비워 두면 됩니다. **다음** 을 클릭합니다.

12. ESM 관리자 인증서 가져오기 창이 표시됩니다. 대상에서 커넥터로 인증서 **가져오기 를 선택하고** 다음 을 **클릭합니다.** 커넥터 **추가 요약** 창이 표시되고 인증서를 가져올 수 있습니다.

13. 커넥터 추가 요약 창의 세부 **정보가** 올바른지 확인한 후 다음 을 **클릭합니다.**

14. 서비스로 **설치를 선택하고** 다음 을 **클릭합니다.**

15. 서비스 내부 이름 **필드에 이름을 입력합니다.** 양식의 다른 모든 값은 기본값으로 유지하거나 비워 두면 됩니다. **다음** 을 클릭합니다.

16. 서비스 매개 변수를 입력하고 다음 을 **클릭합니다.** 서비스 설치 요약 **창이** 표시됩니다. **다음** 을 클릭합니다.

17. 끝내기 및 다음 **을** 선택하여 설치를 **완료합니다.**

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>마이크로 포커스 ArcSight 콘솔 설치 및 구성

1. 다음 작업을 수행하여 설치 마법사를 수행합니다.
   - 소개
   - 사용권 계약
   - 특별 알림
   - ArcSight 설치 디렉터리 선택
   - 바로 가기 폴더 선택
   - 사전 설치 요약

2. **설치** 를 클릭합니다. 설치가 완료되면 ArcSight 콘솔 구성 마법사가 열립니다.

3. 관리자 호스트 이름에 **localhost를** 입력하고 관리자 포트에 8443을 **입력한** 후 다음 을 **클릭합니다.**

4. 직접 **연결 사용을 선택하고** 다음 을 **클릭합니다.**

5. 암호 **기반 인증을 선택하고** 다음 을 **클릭합니다.**

6. 단일 **사용자 설치를 선택합니다. (권장)** 를 클릭한 후 다음 을 **클릭합니다.**

7. **완료를** 클릭하여 설치 관리자를 종료합니다.

8. 마이크로 포커스 ArcSight 콘솔에 로그인합니다.

9. 활성 채널 **집합 새** \> **조건 장치** 장치 \>  \> **제품으로 이동합니다.**

10. 장치 **제품 설정 = Microsoft Defender ATP**. 이벤트가 도구로 흐르고 있는 것이 확인되면 프로세스를 다시 중지하고 Windows 서비스로 이동하고 ArcSight FlexConnector REST를 시작하십시오.

이제 마이크로 포커스 ArcSight 콘솔에서 쿼리를 실행할 수 있습니다.

끝점 검색에 대한 Defender는 공급업체로 "Microsoft"를, 장치 이름으로 "Windows Defender ATP"로 표시됩니다.

## <a name="troubleshooting-micro-focus-arcsight-connection"></a>마이크로 포커스 ArcSight 연결 문제 해결

**문제:** 토큰을 새로 고치지 못했습니다. C: folder_location \\ \current\logs에 있는 로그를 찾을  수 folder_location 도구를 설치한 위치를 나타내는 로그를 찾을 수 있습니다. _agent.log를 열고_ 을 찾아 을 찾아야 `ERROR/FATAL/WARN` 합니다.

**증상:** 다음과 같은 오류 메시지가 표시됩니다.

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**해결 방법:**

1. 커넥터 창에서 Ctrl + C를 클릭하여 프로세스를 중지합니다. **"일괄 처리 작업 종료 Y/N?"을** 요청하면 Y를 클릭합니다.

2. WDATP-connector.properties 파일을 저장한 폴더로 이동한 후 편집하여 다음 값을 추가합니다.

   `reauthenticate=true`.

3. 다음 명령을 실행하여 커넥터를 다시 시작합니다.

   `arcsight.bat connectors`.

   브라우저 창이 나타납니다. 실행을 허용하면 사라지고 커넥터가 실행 중이 됩니다.

> [!NOTE]
> 프로세스를 다시 중지하여 커넥터가 실행되고 있는지 확인해야 합니다. 그런 다음 커넥터를 다시 시작하면 브라우저 창이 나타나지 않습니다.

## <a name="related-topics"></a>관련 항목

- [Endpoint용 Defender에서 SIEM 통합 사용](enable-siem-integration.md)
- [SIEM 도구로 검색 끌어오기](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [REST API를 사용하여 끝점 검색을 위한 Defender 끌어오기](pull-alerts-using-rest-api.md)
- [SIEM 도구 통합 문제 해결](troubleshoot-siem.md)
