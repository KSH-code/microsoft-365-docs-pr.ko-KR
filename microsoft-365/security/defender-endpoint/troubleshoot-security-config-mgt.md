---
title: 끝점용 Microsoft Defender의 보안 관리와 관련된 온보딩 문제 해결
description: 끝점용 Microsoft Defender에 대한 보안 관리를 사용하여 장치를 온보딩하는 동안 발생할 수 있는 문제를 해결합니다.
keywords: 온보더링, 온보더링 문제, 이벤트 뷰어, 데이터 수집 및 미리 보기 빌드, 센서 데이터 및 진단 문제 해결
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 4540336aeea4283f1b5adcab3164e0405ae075c7
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064442"
---
# <a name="troubleshoot-onboarding-issues-related-to-security-management-for-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender의 보안 관리와 관련된 온보딩 문제 해결 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [사용자 계정이 있는 장치에서 끝점에 대한 Microsoft Defender Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender for Endpoint용 보안 관리는 Microsoft Defender에 대한 보안 구성을 수신하기 위해 Microsoft Endpoint Manager 또는 Microsoft Intune Microsoft Endpoint Configuration Manager 관리되지 않는 장치에 대한 기능입니다. 에서 직접 Endpoint Manager.
끝점용 Microsoft Defender의 보안 관리에 대한 자세한 내용은 Manage [Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager.](/mem/intune/protect/mde-security-integration)

끝점용 Microsoft Defender 온보딩 지침에 대한 보안 관리는 끝점 보안 구성 [관리용 Microsoft Defender를 참조하세요.](security-config-management.md)

이 종단 간 온보더링은 마찰 없이 설계될 수 있으며 사용자 입력이 필요하지 않습니다. 그러나 온보딩하는 동안 문제가 발생하는 경우 끝점용 Microsoft Defender 플랫폼 내에서 오류를 보고 문제를 해결할 수 있습니다.


>[!NOTE]
> 새 장치에 대한 온보딩 흐름에 문제가 있는 경우 [끝점용 Microsoft Defender](/mem/intune/protect/mde-security-integration#prerequisites) 선행 단계를 검토하고 온보딩 지침을 따르는지 검토하세요.


클라이언트 분석기에 대한 자세한 내용은 Endpoint 클라이언트 분석기용 Microsoft Defender를 사용하여 센서 상태 문제 [해결을 참조하세요.](/microsoft-365/security/defender-endpoint/overview-client-analyzer)

## <a name="registering-domain-joined-computers-with-azure-active-directory"></a>도메인에 가입된 컴퓨터를 도메인에 Azure Active Directory  
장치를 성공적으로 등록하려면 Azure Active Directory 다음을 보장해야 합니다. 

- 컴퓨터가 도메인 컨트롤러를 사용하여 인증할 수 있습니다. 
- 컴퓨터는 조직의 네트워크 내에서 다음 Microsoft 리소스에 액세스할 수 있습니다.
  - https://enterpriseregistration.windows.net
  - https://login.microsoftonline.com
  - https://device.login.microsoftonline.com
- Azure AD connect는 컴퓨터 개체를 동기화하도록 구성됩니다. 기본적으로 컴퓨터 는 Azure AD connect 동기화 범위에 있습니다. 컴퓨터 개체가 특정 US(조직 구성 단위)에 속하는 경우 Azure AD 2013에서 동기화하도록 커넥트. Azure AD 10을 사용하여 컴퓨터 개체를 동기화하는 방법에 대한 자세한 내용은 커넥트 단위 기반 [필터링을 참조하세요.](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering#organizational-unitbased-filtering)

>[!IMPORTANT]
>Azure AD connect는 R2 컴퓨터 Windows Server 2012 동기화하지 않습니다. 끝점용 Microsoft Defender의 보안 관리를 위해 Azure AD에 등록해야 하는 경우 해당 컴퓨터 개체를 동기화 범위에 포함하기 위해 Azure AD connect 동기화 규칙을 사용자 지정해야 합니다. 에서 컴퓨터 가입 규칙을 적용하는 방법에 대한 [지침을 Azure Active Directory 커넥트.]()

>[!NOTE]
>장치의 운영 체제에 독립적인 온보더링 흐름을 성공적으로 완료하기 위해 장치의 Azure Active Directory 상태는 장치의 초기 상태를 기반으로 변경될 수 있습니다.<br>
>
>|      장치 상태 시작     |      새 장치 상태     |
>|---|---|
>|     이미 AADJ 또는 HAADJ    |     그대로 유지    |
>|     AADJ 또는 하이브리드 Azure Active Directory(HAADJ) + 도메인 가입 안 함    |     장치가 HAADJ'd인 경우    |
>|     AADJ 또는 HAADJ + 도메인에 가입되지 않습니다.    |     장치가 AADJ'd인 경우    |
>
>여기서 AADJ는 joined를 Azure Active Directory HAADJ는 Hybrid Azure Active Directory Joined를 나타 내는 것입니다.


## <a name="troubleshoot-errors-from-the-microsoft-defender-for-endpoint-portal"></a>Endpoint 포털용 Microsoft Defender에서 발생하는 오류 문제 해결


끝점용 Microsoft Defender 포털을 통해 보안 관리자는 이제 끝점 온보딩을 위한 Microsoft Defender에 대한 보안 관리 문제를 해결할 수 있습니다. 


**Endpoints > 장치** 인벤토리에서 관리되는 사용자 열이 관리 채널(예: MEM)을 필터링하기 위해 추가되었습니다. 


:::image type="content" alt-text="장치 인벤토리 페이지의 이미지" source="./images/device-inventory-mde-error.png":::

끝점용 Microsoft Defender 온보딩 프로세스에 대한 보안 관리에 실패한 모든 장치 목록을 표시하기 위해 **MDE-Error로 테이블을 필터링합니다.**

목록에서 특정 장치를 선택하여 사이드 패널에서 문제 해결 세부 정보, 오류의 근본 원인 및 해당 설명서를 확인합니다.


:::image type="content" alt-text="필터링된 장치 인벤토리 페이지의 이미지" source="./images/secconfig-mde-error.png":::


## <a name="run-microsoft-defender-for-endpoint-client-analyzer-on-windows"></a>Microsoft Defender for Endpoint Client Analyzer를 Windows 

끝점 온보딩 흐름에 대한 Microsoft Defender에 대한 보안 관리를 완료하지 못하는 끝점에서 클라이언트 분석기를 실행하는 것이 있습니다. 클라이언트 분석기에 대한 자세한 내용은 Endpoint 클라이언트 분석기용 Microsoft Defender를 사용하여 센서 상태 문제 [해결을 참조하세요.](overview-client-analyzer.md)

클라이언트 분석기 출력 파일(MDE 클라이언트 분석기 Results.htm)은 주요 문제 해결 정보를 제공할 수 있습니다.

- 장치 OS가 일반 장치 세부 정보 섹션에서 끝점 온보딩 흐름에 대한 Microsoft Defender의 보안 관리 범위에 **있는지** 확인합니다.
- 장치가 장치 구성 관리 세부 정보에서 Azure Active Directory 등록되어 있는지 **확인합니다.**


    ![클라이언트 분석기 결과의 이미지](images/client-analyzer-results.png)


보고서의 **자세한** 결과 섹션에서 클라이언트 분석기는 실행 가능한 지침도 제공합니다.

>[!TIP]
>보고서의 자세한 결과 섹션에 "오류"가 포함되어 있지 않은지 확인한 다음 모든 "경고" 메시지를 검토해야 합니다.

예를 들어 보안 관리 온보딩 흐름의 일부로, 보고서의 장치 구성 관리 세부 정보 섹션에 나타나는 SCP 테넌트 ID와 일치하려면  끝점 테넌트용 Microsoft Defender의 Azure Active Directory 테넌트 ID가 필요합니다. 해당되는 경우 보고서 출력에서 이 확인을 수행하는 것이 좋습니다.

![자세한 결과의 이미지](images/detailed-results.png)


## <a name="general-troubleshooting"></a>일반 문제 해결 

AAD 또는 MEM에서 등록된 장치를 식별할 수 없는 경우 등록 중에 오류가 발생하지 않은 경우 레지스트리 키를 확인하면 추가 문제 해결 정보를 제공할 수 `Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SenseCM\\EnrollmentStatus` 있습니다.  

:::image type="content" alt-text="등록 상태의 이미지입니다." source="images/enrollment-status.png":::

다음 표에는 오류를 해결하기 위해 시도/확인할 오류 및 길안이 나열됩니다. 오류 목록은 완료되지 않은 것으로, 과거에 고객이 발생한 일반적인 오류를 기반으로 합니다. 


| 오류 코드                    | 등록 상태                     | 관리자 작업                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-------------------------------|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``5-9``,``11-12``, ``26-33``  |일반 오류                          |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 보안 구성 관리 흐름에 오류가 발생했습니다. 디바이스가 끝점 관리 채널용 Microsoft Defender에 대한 사전 사전을 모임하지 [못하기 때문일 수 있습니다.](security-config-management.md) 장치에서 [클라이언트 분석기를](https://aka.ms/BetaMDEAnalyzer) 실행하면 문제의 근본 원인을 파악하는 데 도움이 될 수 있습니다. 도움이되지 않는 경우 지원에 문의하시기 바랍니다.   |
| ``13-14``,``20``,``24``,``25``|연결 문제                     |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 연결 문제로 인해 보안 구성 관리 흐름에 오류가 발생했습니다. 방화벽에서 Azure Active Directory [Microsoft Endpoint Manager 끝점이](security-config-management.md#connectivity-requirements) 열립니다.                                                                                       |
| ``10``,``42``                 |일반 하이브리드 조인 실패            |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 보안 구성 관리 흐름에 오류가 발생하고 OS가 하이브리드 조인을 수행하지 못했습니다. OS [수준 하이브리드 Azure Active Directory 문제를](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current) 해결하기 위해 하이브리드 연결 장치 문제 해결을 사용 합니다.                                                                                                                               |
| ``15``                        |테넌트 불일치                        |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 끝점 테넌트 ID에 대한 Microsoft Defender가 Azure Active Directory 테넌트 ID와 일치하지 않는 경우 보안 구성 관리 흐름에 오류가 발생했습니다. 끝점 테넌트용 Defender의 Azure Active Directory 테넌트 ID가 도메인의 SCP 항목의 테넌트 ID와 일치하는지 확인 자세한 내용은 [Endpoint용 Microsoft Defender의](troubleshoot-security-config-mgt.md)보안 관리와 관련된 온보딩 문제 해결을 참조합니다.|
| ``16``,``17``                 |하이브리드 오류 - 서비스 연결 지점|장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 SCP(서비스 연결 지점) 레코드가 올바르게 구성되지 않은 경우 장치를 Azure AD에 가입할 수 없습니다. DRS에 가입하도록 SCP가 Enterprise 있습니다. SCP 레코드가 해당 레코드를 AAD 모범 사례에 따라 구성해야 합니다. 자세한 내용은 [Configure a service connection point을 참조하십시오.](/azure/active-directory/devices/hybrid-azuread-join-manual#configure-a-service-connection-point)                                                      |
| ``18``                        |인증서 오류                      |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 장치 인증서 오류로 인해 보안 구성 관리 흐름에 오류가 발생했습니다. 장치 인증서는 다른 테넌트에 속합니다. 신뢰할 수 있는 인증서 프로필을 만들 때 모범 [사례가 따르는지 확인](/mem/intune/protect/certificates-trusted-root#create-trusted-certificate-profiles)                                                                                                    |
| ``36``                        |LDAP API 오류                         |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 보안 구성 관리 흐름에 오류가 발생했습니다. 네트워크 토폴로지 확인 및 하이브리드 조인 요청을 완료하는 데 LDAP API를 사용할 수 있는지 확인합니다.     |
| ``37``                        |사내 동기화 문제                  |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 보안 구성 관리 흐름에 오류가 발생했습니다. 나중에 다시 시도합니다. 그래도 도움이되지 않는 경우 Azure AD와 개체 동기화 문제 해결을 [커넥트 참조하세요.](/azure/active-directory/hybrid/tshoot-connect-objectsync)|
| ``38``,``41``                 |DNS 오류                              |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 DNS 오류로 인해 보안 구성 관리 흐름에 오류가 발생했습니다. 장치에서 인터넷 연결 및/또는 DNS 설정을 확인합니다. 잘못된 DNS 설정이 Workstation 쪽에 있을 수 있습니다. Active Directory를 사용하려면 도메인 DNS를 사용하여 제대로 작동해야 합니다(라우터의 주소가 아니라). 자세한 내용은 [Endpoint용 Microsoft Defender의](troubleshoot-security-config-mgt.md)보안 관리와 관련된 온보딩 문제 해결을 참조하세요.             |
| ``40``                        |시계 동기화 문제                       |장치가 끝점용 Microsoft Defender에 성공적으로 온보딩된 경우 그러나 보안 구성 관리 흐름에 오류가 발생했습니다. 시계가 올바르게 설정되어 있으며 오류가 발생하는 디바이스에서 동기화되어 있는지 확인합니다.    |


## <a name="azure-active-directory-runtime-troubleshooting"></a>Azure Active Directory 런타임 문제 해결 

### <a name="azure-active-directory-runtime"></a>Azure Active Directory 런타임  

AADRT(Azure Active Directory 런타임)의 문제를 해결하는 주요 메커니즘은 디버그 추적을 수집하는 것입니다. Azure Active Directory Windows 런타임에서는 **ID가 bd67e65c-9cc2-51d8-7399-0bb9899e75c1인 ETW** 공급자를 사용합니다. ETW 추적은 실패를 재현하여 캡처해야 합니다(예: 조인 실패가 발생하는 경우 조인을 수행하기 위해 AADRT API 호출을 다루는 기간 동안 추적을 사용하도록 설정해야 합니다.  

AADRT 로그의 일반적인 오류와 이 오류를 읽는 방법에 대한 자세한 내용은 아래를 참조하세요. 

![이벤트 속성의 이미지](images/event-properties.png)

메시지의 정보에서 대부분의 경우 발생하는 오류, 오류를 반환한 Win32 API(해당되는 경우), 사용된 URL(해당하는 경우), 런타임 API 오류가 AAD 수 있습니다. 
  
 

## <a name="instructions-for-applying-computer-join-rule-in-aad-connect"></a>2016에서 컴퓨터 가입 규칙을 적용하기 위한 AAD 커넥트 

Windows Server 2012 도메인에 가입된 컴퓨터의 Microsoft Defender for Endpoint에 대한 보안 관리의 경우 Azure AD 커넥트 동기화 규칙 "AD-Computer 가입에서"에 대한 업데이트가 필요합니다. 이는 원래 "AD에서 컴퓨터 가입" 규칙을 사용하지 않도록 설정하는 규칙을 복제하고 수정하여 달성할 수 있습니다. Azure AD 커넥트 기본 제공 규칙을 변경할 수 있는 이 환경을 제공합니다.

>[!NOTE]
>이러한 변경 내용은 서버가 실행 중인 서버에 AAD 커넥트 합니다. 배포된 인스턴스가 여러 AAD 커넥트 모든 인스턴스에 이러한 변경 내용을 적용해야 합니다. 

1. 시작 메뉴에서 동기화 규칙 편집기 응용 프로그램을 열 수 있습니다. 규칙 목록에서 **AD에서 In – Computer Join 이라는 규칙을 찾습니다.** **이 규칙의 '우선 순위' 열에 있는 값을 유의합니다.** 

    ![동기화 규칙 편집기 이미지](images/57ea94e2913562abaf93749d306dd6cf.png)

2. IN **from AD – Computer Join 규칙이** 강조 표시된 경우 편집 을 **선택합니다.** 예약된 **규칙 확인 편집** 대화 상자에서 예를 **선택합니다.** 

   ![예약된 규칙 확인 편집 이미지](images/8854440d6180a5580efda24110551c68.png)

3. **인바운드 동기화 규칙** 편집 창이 표시됩니다. 이 규칙을 사용하여 Windows Server 2012R2가 동기화되도록 규칙 설명을 업데이트합니다. 우선 순위 값을 제외한 다른 모든 옵션은 그대로 두면 됩니다. 규칙 목록에 표시한 원래 규칙의 값보다 큰 우선 순위 값을 입력합니다.  

   ![확인 이미지](images/ee0f29162bc3f2fbe666c22f14614c45.png)

4.  다음을 **세** 번 선택합니다. 이렇게 하면 규칙의 '변환' 섹션으로 이동합니다. 규칙의 '스쿠핑 필터' 및 '조인 규칙' 섹션을 변경하지 않습니다. 이제 '변환' 섹션이 표시됩니다. 

    ![인바운드 동기화 규칙의 이미지](images/296f2c2a705e41233631c3784373bc23.png)

5. 변환 목록의 아래쪽으로 스크롤합니다. **cloudFiltered** 특성에 대한 변환을 찾아 찾습니다. 원본 열의 텍스트  상자에서 모든 텍스트(Control-A)를 선택하고 삭제합니다. 이제 텍스트 상자가 비어 있습니다. 

6. 새 규칙의 콘텐츠를 텍스트 상자에 붙여 넣습니다. 


    ```command
    IIF(
      IsNullOrEmpty([userCertificate])
      || 
      (
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        && 
        (Left([operatingSystemVersion],2) = "6.")
        &&
        (Left([operatingSystemVersion],3) <> "6.3")
      )
      ||
      (
        (Left([operatingSystemVersion],3) = "6.3") 
        &&
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        With(
          $validCerts,
          Where(
            $c, 
            [userCertificate], 
            IsCert($c) && CertNotAfter($c) > Now() && RegexIsMatch(CertSubject($c), "CN=[{]*" & StringFromGuid([objectGUID]) & "[}]*", "IgnoreCase")),
          Count($validCerts) = 0)
      ),
      True,
      NULL
    )

    ```

7.  **저장을** 선택하여 새 규칙을 저장합니다.

## <a name="related-topic"></a>관련 항목
- [사용자 계정이 있는 장치에서 끝점에 대한 Microsoft Defender Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
