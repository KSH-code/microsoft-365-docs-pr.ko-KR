---
title: 보고서 메시지 또는 보고서 피싱 추가 기능 사용
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 보고서 메시지 또는 보고서 피싱 추가 기능을 Outlook 및 웹용 Outlook, 개별 사용자 또는 전체 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정하는 방법을 학습합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b87367ed46f51d3569c900ba2661aaf34209de4
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60705200"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>보고서 메시지 또는 보고서 피싱 추가 기능 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 사서함이 있는 Microsoft 365 조직의 관리자는 Exchange Online 포털의 제출 페이지를 사용하는 Microsoft 365 Defender 좋습니다.  자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)

Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 가음성(나쁜 것으로 표시된 양호한 전자 메일) 또는 거짓 부정(잘못된 전자 메일 허용)을 분석을 위해 Microsoft 및 계열사에 쉽게 보고할 수 있습니다.

Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다. 예를 들어 피싱 보고 추가 기능을 사용하여 많은 메시지를 보고하는 사람이 많은 경우를 가정해 보겠습니다. 이 정보는 보안 대시보드 및 기타 보고서에 표시됩니다. 조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있습니다.

보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다. 사용자가 스팸 및 피싱 메시지를 모두 보고하게 하려는 경우 조직에 보고서 메시지 추가 기능을 배포합니다.

보고서 메시지 추가 기능은 스팸 및 피싱 메시지를 모두 보고하는 옵션을 제공합니다. 관리자는 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.

피싱 보고 추가 기능은 피싱 메시지만 보고하는 옵션을 제공합니다. 관리자는 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다.

개별 사용자인 경우 추가 기능을 모두 사용하도록 설정할 수 있습니다.

전역 관리자 또는 Exchange Online 관리자로서 Exchange OAuth 인증을 사용하도록 구성된 경우 조직에 대해 보고서 메시지 추가 기능 및 피싱 보고 추가 기능을 사용하도록 설정할 수 있습니다. 이제 중앙 집중식 배포를 통해 두 추가 [기능을 모두 사용할 수 있습니다.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 보고서 메시지 추가 기능 및 피싱 보고 추가 기능 모두 대부분의 Microsoft 365 및 다음 제품을 사용할 수 있습니다.
  - 웹용 Outlook
  - Outlook 2013 SP1 이상
  - Mac용 Outlook 2016
  - Outlook 앱용 Microsoft 365 포함된 Enterprise
  - Outlook iOS 및 Android용 앱

- 두 추가 기능을 모두 공유 사서함 또는 조직에 있는 사서함에 사용할 Exchange 없습니다.

- 기존 웹 브라우저는 보고서 메시지와 피싱 보고 추가 기능 둘 다에서 작동해야 합니다. 그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 사용해 보십시오.

- 조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다. 자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)

- 관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다. 자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.

- 보고서 메시지 기능을 사용하여 메시지를 보고하는 방법에 대한 자세한 내용은 report [false positives and false negatives in Outlook.](report-false-positives-and-false-negatives.md)

- URL 필터링 또는 보안 솔루션(예: 프록시 및/또는 방화벽)이 있는 조직에는 HTTPS 프로토콜에서 ipagave.azurewebsites.net outlook.office.com 끝점에 도달할 수 있어야 합니다.


> [!IMPORTANT]
> 사용자 제출 정책을 사용할 수 Outlook 기본 제공 보고 환경은 사용하지 [않는 것이 좋습니다.](./user-submission.md) 대신 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하는 것이 좋습니다.

## <a name="get-the-report-message-add-in"></a>보고서 메시지 추가 기능 확인

### <a name="get-the-report-message-add-in-for-yourself"></a>직접 보고서 메시지 추가 기능 확인

1. 에서 Microsoft AppSource로 이동하여 보고서 메시지 추가 기능을 <https://appsource.microsoft.com/marketplace/apps> 검색합니다. 보고서 메시지 추가 기능으로 직접 이동하기 위해 로 <https://appsource.microsoft.com/product/office/wa104381180> 이동하십시오.

2. 지금 **다운로드를 클릭합니다.**

   ![보고서 메시지 - 지금 얻습니다.](../../media/ReportMessageGETITNOW.png)

3. 나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**

4. 직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.

추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.

- 이 Outlook 아이콘은 다음과 같습니다.

    > [!div class="mx-imgBorder"]
    > ![보고서 메시지 추가 기능 아이콘을 Outlook.](../../media/OutlookReportMessageIcon.png)

- 이 웹용 Outlook 아이콘은 다음과 같습니다.

    > [!div class="mx-imgBorder"]
    > ![웹용 Outlook 보고서 메시지 추가 기능 아이콘입니다.](../../media/owa-report-message-icon.png)

### <a name="get-the-report-message-add-in-for-your-organization"></a>조직에 대한 보고서 메시지 추가 기능 확인

> [!NOTE]
> 추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.

1. 에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home?#/homepage)통합 **설정** \> **로 이동하세요.** 앱 **다운로드를 클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 관리 센터 통합 앱](../../media/microsoft-365-admin-center-integrated-apps.png)

2. 나타나는 **Microsoft 365 앱** 페이지에서 검색 상자를 **클릭하고** 보고서 **메시지** 를 입력한 다음 검색 검색 **아이콘을** ![ ](../../media/search-icon.png) 클릭합니다. 결과 목록에서 보고서 메시지 **를 찾아 선택합니다.** 

3. 앱 세부 정보 페이지가 열립니다. 지금 **바로 가기 를 선택합니다.** 

    > [!div class="mx-imgBorder"]
    > ![보고서 메시지 추가 기능](../../media/microsoft-365-admin-center-report-message.png)  

4. 기본 프로필 정보를 완료한 다음 계속을 **클릭합니다.** 

    > [!div class="mx-imgBorder"]
    > ![메시지 추가 기능 프로필 설정 보고](../../media/microsoft-365-admin-center-profile-info.png)

5. 새 **앱 배포** 플라이아웃이 열립니다. 다음 설정을 구성합니다. **다음을** 클릭하여 다음 페이지로 이동하여 설정을 완료합니다. 

   - **사용자 추가:** 다음 값 중 하나를 선택합니다.
     - **저뿐이에요**
     - **전체 조직**
     - **특정 사용자/그룹**

   - **배포**:
     - **사용 권한 요청** 수락: 다음 페이지로 이동하기 전에 앱 사용 권한 및 기능을 신중하게 읽어 읽습니다.

        > [!div class="mx-imgBorder"]
        > ![앱 사용 권한](../../media/microsoft-365-admin-center-deploy-new-app.png)

     - **배포 완료:** 추가 기능 배포를 검토하고 완료합니다. 
     - **배포 완료:** **완료를** 선택하여 설치를 완료합니다. 

        > [!div class="mx-imgBorder"]
        > ![배포 완료](../../media/microsoft-365-admin-center-deployment-complete.png)

## <a name="edit-settings-for-the-report-message-add-in"></a>보고서 메시지 추가 기능 설정 편집

1. 이 Microsoft 365 관리 센터 통합 앱으로 **설정** \> **이동하세요.** \. 그런 다음 보고서 **메시지** 추가 기능을 찾아 선택합니다.

2. 플라이아웃이 나타나면 사용자  편집을 선택하여 사용자 설정을 편집합니다.

    > [!div class="mx-imgBorder"]
    > ![보고서 메시지 플라이아웃](../../media/microsoft-365-admin-center-report-message-edit.png)

3. 추가 기능을 제거하려면 동일한  플라이아웃의 작업에서 **앱** 제거를 선택합니다. 

## <a name="get-the-report-phishing-add-in"></a>피싱 보고서 추가 기능 얻기

### <a name="get-the-report-phishing-add-in-for-yourself"></a>직접 피싱 보고 추가 기능 사용

1. 에서 Microsoft AppSource로 이동하여 피싱 보고 추가 <https://appsource.microsoft.com/marketplace/apps> 기능을 검색합니다.

2. 지금 **다운로드를 클릭합니다.**

3. 나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**

4. 직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.

추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.

- 이 Outlook 아이콘은 다음과 같습니다.

  ![피싱 추가 기능 아이콘을 보고하여 Outlook.](../../media/Outlook-ReportPhishing.png)

- 이 웹용 Outlook 아이콘은 다음과 같습니다.

    > [!div class="mx-imgBorder"]
    > ![웹용 Outlook 피싱 추가 기능 아이콘 보고](../../media/OWA-ReportPhishing.png)

### <a name="get-the-report-phishing-add-in-for-your-organization"></a>조직의 피싱 보고 추가 기능 확인

> [!NOTE]
> 추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.

1. 에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/Home?#/homepage)통합 **설정** \> **로 이동하세요.** 앱 **다운로드를 클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 관리 센터 통합 앱](../../media/microsoft-365-admin-center-integrated-apps.png)

2. 나타나는 **Microsoft 365 앱** 페이지에서 검색 상자를 **클릭하고** 피싱 **보고를** 입력한 다음 검색 검색 **아이콘을** ![ 클릭합니다. ](../../media/search-icon.png) 결과 목록에서 피싱 **보고 를 찾아 선택합니다.** 
 
3. 앱 세부 정보 페이지가 열립니다. 지금 **바로 가기 를 선택합니다.**

4. 기본 프로필 정보를 완료한 다음 계속을 **클릭합니다.**

5. 새 **앱 배포** 플라이아웃이 열립니다. 위에 [설명된 단계에 따라](enable-the-report-message-add-in.md#get-the-report-message-add-in-for-your-organization) 설정을 완료합니다. 

## <a name="edit-settings-for-the-report-phishing-add-in"></a>피싱 보고 추가 기능 설정 편집

1. 이 Microsoft 365 관리 센터 통합 앱으로 **설정** \> **이동하세요.** \. 그런 다음 피싱 **보고 추가** 기능을 찾아 선택합니다.

2. 플라이아웃이 나타나면 사용자  편집을 선택하여 사용자 설정을 편집합니다.

    > [!div class="mx-imgBorder"]
    > ![피싱 플라이아웃 보고](../../media/microsoft-365-admin-center-report-phishing-edit.png)

3. 추가 기능을 제거하려면 동일한  플라이아웃의 작업에서 **앱** 제거를 선택합니다. 
