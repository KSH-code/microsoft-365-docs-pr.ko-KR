---
title: 끝점용 Microsoft Defender의 SIEM 도구 통합 문제 해결
description: Microsoft Defender for Endpoint에서 SIEM 도구를 사용할 때 발생할 수 있는 문제를 해결합니다.
keywords: 문제 해결, siem, 클라이언트 비밀, 비밀
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 95b4b82b87fc633afe716c9c7b403808bedac65d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213392"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>SIEM 도구 통합 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

SIEM 도구에서 검색을 끌어오는 동안 문제를 해결해야 할 수 있습니다.

이 페이지에서는 발생할 수 있는 문제를 해결하기 위한 자세한 단계를 제공합니다.

## <a name="learn-how-to-get-a-new-client-secret"></a>새 클라이언트 비밀을 얻는 방법 학습

클라이언트 비밀이 만료되거나 SIEM 도구 응용 프로그램을 사용하도록 설정하는 경우 제공된 복사본을 잘못 저장한 경우 새 비밀을 얻게 됩니다.

1. Azure 관리 [포털에 로그인합니다.](https://portal.azure.com)

2. **Azure Active Directory** 를 선택합니다.

3. 테넌트 선택

4. 앱 **등록 을 클릭합니다.** 그런 다음 응용 프로그램 목록에서 응용 프로그램을 선택합니다.

5. 인증서 **& 섹션을** 선택하고 새 클라이언트 비밀을 클릭한 다음 설명을 제공하고 유효 기간을 지정합니다.

6. **저장** 을 클릭합니다. 키 값이 표시됩니다.

7. 값을 복사하여 안전한 장소에 저장합니다.

## <a name="error-when-getting-a-refresh-access-token"></a>새로 고침 액세스 토큰을 사용할 때 오류 발생

위협 인텔리전스 API 또는 SIEM 도구를 사용할 때 새로 고침 토큰을 얻려고 할 때 오류가 발생하는 경우 해당 응용 프로그램에 대한 회신 URL을 추가해야 Azure Active Directory.

1. Azure 관리 [포털에 로그인합니다.](https://ms.portal.azure.com)

2. **Azure Active Directory** 를 선택합니다.

3. 테넌트 선택

4. 앱 **등록 을 클릭합니다.** 그런 다음 응용 프로그램 목록에서 응용 프로그램을 선택합니다.

5. 다음 URL을 추가합니다.
   - 유럽 연합의 경우: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - 영국의 경우: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - 미국의 경우:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .

6. **저장** 을 클릭합니다.

## <a name="error-while-enabling-the-siem-connector-application"></a>SIEM 커넥터 응용 프로그램을 사용하도록 설정하는 동안 오류가 발생했습니다.

SIEM 커넥터 응용 프로그램을 사용하도록 설정할 때 오류가 발생하는 경우 브라우저의 팝업 차단 설정을 확인합니다. 이 기능을 사용하도록 설정하면 새 창이 열리게 차단될 수 있습니다.

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)

## <a name="related-topics"></a>관련 항목

- [끝점용 Microsoft Defender에서 SIEM 통합 사용](enable-siem-integration.md)
- [끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight 구성](configure-arcsight.md)
- [SIEM 도구로 검색 끌어오기](configure-siem.md)
- [끝점 검색 필드용 Microsoft Defender](api-portal-mapping.md)
- [REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기](pull-alerts-using-rest-api.md)
