---
title: 끝점용 Microsoft Defender에서 SIEM 통합 사용
description: SIEM(보안 정보 및 이벤트 관리) 솔루션에서 검색을 수신하려면 SIEM 통합을 사용하도록 설정하세요.
keywords: siem 커넥터, siem, 커넥터, 보안 정보 및 이벤트 사용
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
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076244"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 SIEM 통합 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)


>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

Microsoft Defender 보안 센터에서 검색을 끌어오기 위해 SIEM(보안 정보 및 이벤트 관리) 통합을 사용하도록 설정하세요. SIEM 솔루션을 사용하여 검색을 끌어오거나 검색 REST API에 직접 연결합니다.

>[!NOTE]
>- [끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.
>- [끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.
>- 끝점 경고용 Microsoft Defender 경고 API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 포함 합니다. 자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)

## <a name="prerequisites"></a>필수 구성 요소

- 설정을 활성화하는 사용자에게는 AAD(Azure Active Directory)에서 앱을 만들 수 있는 권한이 있어야 합니다. 이 역할은 다음과 같은 역할을 합니다. 

  - 보안 관리자 및 전역 관리자
  - 클라우드 응용 프로그램 관리자
  - 응용 프로그램 관리자
  - 서비스 보안 주체의 소유자

- 초기 활성화 중에 자격 증명을 입력할 수 있는 팝업 화면이 표시됩니다. 이 사이트에 대해 팝업을 허용해야 합니다.

## <a name="enabling-siem-integration"></a>SIEM 통합 사용 
1. 탐색 창에서 설정   >  **SIEM 을 선택합니다.**

    ![설정 메뉴의 SIEM 통합 이미지1](images/enable_siem.png)

    >[!TIP]
    >SIEM 커넥터 응용 프로그램을 사용하도록 설정할 때 오류가 발생하는 경우 브라우저의 팝업 차단 설정을 확인합니다. 이 기능을 사용하도록 설정하면 새 창이 열리게 차단될 수 있습니다. 

2. **SIEM 통합 사용 을 선택합니다.** 이렇게 하면 미리 채워진 값을 사용하여 **SIEM** 커넥터 액세스 세부 정보 섹션이 활성화되면 Azure AD(Azure Active Directory) 테넌트 아래에 응용 프로그램이 만들어집니다.

    > [!WARNING]
    >클라이언트 비밀은 한 번만 표시됩니다. 복사본을 안전한 장소에 보관해야 합니다.<br>
     

    ![설정 메뉴2의 SIEM 통합 이미지](images/siem_details.png)

3. 조직에서 사용하는 SIEM 유형을 선택하십시오.

   > [!NOTE]
   > HP ArcSight를 선택하는 경우 다음 두 구성 파일을 저장해야 합니다.<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   프로그래밍 액세스를 통해 검색 REST API에 직접 연결하려면 일반 **API 를 선택하십시오.**

4. 개별 값을 복사하거나 **파일에 세부** 정보 저장을 선택하여 모든 값이 포함된 파일을 다운로드합니다.

5. 토큰 **생성을 선택하여** 액세스 및 새로 고침 토큰을 얻습니다.
  
   > [!NOTE]
   > 90일마다 새 Refresh 토큰을 생성해야 합니다. 

6. 끝점용 [Microsoft Defender에](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) 대한 Azure AD 앱 등록을 만들기 위한 지침을 따르고 경고를 읽을 수 있는 올바른 권한을 할당합니다.

이제 SIEM 솔루션을 구성하거나 프로그래밍 방법을 통해 검색 REST API에 연결할 수 있습니다. Microsoft Defender 보안 센터에서 검색을 받을 수 있도록 SIEM 솔루션을 구성할 때 토큰을 사용해야 합니다.

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>끝점용 Microsoft Defender와 IBM QRadar 통합 
끝점용 Microsoft Defender에서 검색을 수집하도록 IBM QRadar를 구성할 수 있습니다. 자세한 내용은 [IBM 기술 센터를 참조하세요.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

## <a name="see-also"></a>참고 항목
- [끝점 감지를 위해 Microsoft Defender를 끌어오도록 HP ArcSight 구성](configure-arcsight.md)
- [끝점 검색 필드용 Microsoft Defender](api-portal-mapping.md)
- [REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기](pull-alerts-using-rest-api.md)
- [SIEM 도구 통합 문제 해결](troubleshoot-siem.md)
