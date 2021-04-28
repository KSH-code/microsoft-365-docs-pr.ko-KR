---
title: Outlook에서 가짓 긍정 및 거짓 부정 보고
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Outlook에서 가짓 긍정 및 거짓 부정을 보고하고 보고서 메시지 및 피싱 보고 추가 기능을 사용하도록 설정하는 방법을 학습합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065209"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Outlook에서 가짓 긍정 및 거짓 부정 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Exchange Online 사서함이 있는 Microsoft 365 조직의 관리자인 경우 보안 및 준수 센터의 제출 포털을 & 좋습니다. 자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)

하이브리드 최신 인증을 사용하는 사서함이 있는 Microsoft 365 조직 또는 하이브리드 최신 인증을 사용하는 Microsoft 365 조직에서는 가음성(스팸으로 표시된 양호한 전자 메일) 및 거짓 부정(잘못된 전자 메일 및 피싱 허용)을 EOP(Exchange Online Protection)에 제출할 수 있습니다.

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a>보고서 메시지 기능을 사용하기 전에 기억해야 할 것

- 최상의 사용자 제출 환경을 위해 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하세요.

- 이 추가 기능의 작동 방식은 웹, iOS, Android 및 데스크톱 등 모든 플랫폼에서 Outlook에서 작동합니다.

- Exchange Online 사서함이 있는 조직의 관리자인 경우 보안 및 준수 센터의 제출 포털을 & 있습니다. 자세한 내용은 관리 제출을 사용하여 의심되는 스팸, 피싱, URL 및 파일을 Microsoft에 제출을 [참조하세요.](admin-submission.md)

- 메시지를 Microsoft로 직접 보내거나 지정한 사서함 또는 둘 다로 보내도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책 을 참조하세요.](user-submission.md)

- Microsoft에 메시지를 보고하는 데 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-report-message-feature"></a>보고서 메시지 기능 사용

### <a name="report-junk-and-phishing-messages"></a>정크 및 피싱 메시지 보고

받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더에 있는 메시지의 경우 다음 방법을 사용하여 스팸 및 피싱 메시지를 보고합니다.

1. 선택한 **메시지의** 오른쪽 위에 있는 추가 작업 줄임표를  클릭하고 드롭다운 메뉴에서 메시지  보고를 클릭한 다음 정크 또는 피싱 **을 선택합니다.**
  
   > [!div class="mx-imgBorder"]
   > ![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![보고서 메시지 - 정크 및 피싱](../../media/report-message-junk-phishing.png)

2. 선택한 메시지는 분석을 위해 Microsoft로 전송됩니다.

   - 스팸으로 보고된 경우 정크 메일 폴더로 이동되었습니다.

   - 피싱으로 보고된 경우 삭제되었습니다.
   
### <a name="report-messages-that-are-not-junk"></a>정크 메일이 아닌 메시지 보고

1. 선택한 **메시지의** 오른쪽 위 모서리에 있는 추가 작업 줄임표를 클릭하고 드롭다운 메뉴에서 메시지 보고를 클릭한 다음 정크 메일 아님 **을 클릭합니다.**   

   > [!div class="mx-imgBorder"]
   > ![보고서 메시지 - 추가 작업](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![보고서 메시지 - 정크 메일 아님](../../media/report-message-not-junk.png)

2. 선택한 메시지가 분석을 위해 Microsoft로 전송되어 받은 편지함 또는 기타 지정된 폴더로 이동됩니다.

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a>보고서 메시지 및 피싱 보고 추가 기능 사용

Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 피싱 보고 추가 기능을 사용하면 사용자가 분석을 위해 Microsoft 및 계열사에 가음성(나쁜 것으로 표시된 양호한 전자 메일) 또는 거짓 부정(잘못된 전자 메일 허용)을 쉽게 보고할 수 있습니다. 

Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 향상합니다. 예를 들어 피싱 보고 추가 기능을 사용하여 많은 메시지를 보고하는 사람이 많은 경우를 가정해 보겠습니다. 이 정보는 보안 대시보드 및 기타 보고서에 표시됩니다. 조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있습니다. 

보고서 메시지 또는 피싱 보고 추가 기능을 설치할 수 있습니다. 사용자가 스팸 및 피싱 메시지를 모두 보고하게 하려는 경우 조직에 보고서 메시지 추가 기능을 배포합니다. 자세한 내용은 Enable the Report Message add-in을 참조하십시오. 

보고서 메시지 추가 기능은 스팸 및 피싱 메시지를 모두 보고하는 옵션을 제공합니다. 관리자는 조직에 대해 보고서 메시지 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다. 

피싱 보고 추가 기능은 피싱 메시지만 보고하는 옵션을 제공합니다. 관리자는 조직에 대해 피싱 보고 추가 기능을 사용하도록 설정할 수 있으며 개별 사용자는 이를 직접 설치할 수 있습니다. 

개별 사용자인 경우 추가 기능을 모두 사용하도록 설정할 수 있습니다.

f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization. 이제 중앙 집중식 배포를 통해 두 추가 [기능을 모두 사용할 수 있습니다.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 보고서 메시지 추가 기능 및 피싱 보고 추가 기능 모두 대부분의 Microsoft 365 구독 및 다음 제품과 함께 작동합니다.

  - 웹용 Outlook
  - Outlook 2013 SP1 이상
  - Mac용 Outlook 2016
  - 엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook
  - iOS 및 Android용 Outlook 앱

- 두 추가 기능을 모두 공유 사서함 또는 사내 Exchange 조직의 사서함에 사용할 수 없습니다.

- 기존 웹 브라우저는 보고서 메시지와 피싱 보고 추가 기능 둘 다에서 작동해야 합니다. 그러나 추가 기능을 사용할 수 없는 경우 또는 예상대로 작동하지 않는 경우 다른 브라우저를 사용해 보십시오.

- 조직 설치의 경우 OAuth 인증을 사용하도록 조직을 구성해야 합니다. 자세한 내용은 추가 기능의 중앙 집중식 배포가 조직에 [적합한지 확인을 참조하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)

- 관리자는 전역 관리자 역할 그룹의 구성원이 해야 합니다. 자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

## <a name="get-the-report-message-add-in"></a>보고서 메시지 추가 기능 확인

### <a name="get-the-add-in-for-yourself"></a>직접 추가 기능 사용

1. 에서 Microsoft AppSource로 이동하여 보고서 메시지 추가 기능을 <https://appsource.microsoft.com/marketplace/apps> 검색합니다. 보고서 메시지 추가 기능으로 직접 이동하기 위해 로 <https://appsource.microsoft.com/product/office/wa104381180> 이동하십시오.

2. 지금 **다운로드를 클릭합니다.**

   ![보고서 메시지 - 지금 시작](../../media/ReportMessageGETITNOW.png)

3. 나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**

4. 직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.

추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.

- Outlook에서 아이콘은 다음과 같습니다.

  > [!div class="mx-imgBorder"]
  > ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- 웹에서 Outlook에서 아이콘은 다음과 같습니다.

  > [!div class="mx-imgBorder"]
  > ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>조직에 대한 추가 기능 사용

> [!NOTE]
> 추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.

1. Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다. 추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**

2. 페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**

4. 다음 페이지에서 **스토어에서 선택을 클릭합니다.**

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. 나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 보고서 **메시지** 를 입력한 다음 검색 검색 아이콘 **을** ![ ](../../media/search-icon.png) 클릭합니다. 결과 목록에서 보고서 **메시지를 찾은 다음** 추가 를 **클릭합니다.**

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

6. 나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**

7. 나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.

   - **할당된 사용자:** 다음 값 중 하나를 선택합니다.

     - **모든** 사용자(기본값)
     - **특정 사용자/그룹**
     - **저뿐이에요**

   - **배포 방법:** 다음 값 중 하나를 선택합니다.

     - **고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.
     - **사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**
     - **선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   완료되면 배포를 **클릭합니다.**

8. 보고서 **메시지** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다. 정보를 읽은 후 다음 을 **클릭합니다.**

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

9. 추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**

   ![추가 기능 페이지 발표](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>보고서 메시지 추가 기능의 설정 검토 또는 편집

1. Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다. 추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**

   ![새 Add-Ins Microsoft 365 관리 센터의 서비스 및 서비스 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 보고서 메시지 **추가** 기능을 찾아 선택합니다.

3. 보고서 **메시지 편집** 플라이아웃이 나타나면 조직에 적합한 설정을 검토하고 편집합니다. 작업을 마쳤으면 **저장** 을 클릭합니다.

   ![보고서 메시지 추가 기능 설정](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>피싱 보고서 추가 기능 얻기

### <a name="get-the-add-in-for-yourself"></a>직접 추가 기능 사용

1. 에서 Microsoft AppSource로 이동하여 피싱 보고 추가 <https://appsource.microsoft.com/marketplace/apps> 기능을 검색합니다.

2. 지금 **다운로드를 클릭합니다.**

3. 나타나는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 다음 계속을 **클릭합니다.**

4. 직장 또는 학교 계정(업무용) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.

추가 기능을 설치하고 사용하도록 설정하면 다음과 같은 아이콘이 표시됩니다.

- Outlook에서 아이콘은 다음과 같습니다.

  ![Outlook용 피싱 추가 기능 아이콘 보고](../../media/Outlook-ReportPhishing.png)

- 웹에서 Outlook에서 아이콘은 다음과 같습니다.

  > [!div class="mx-imgBorder"]
  > ![웹용 Outlook 보고서 피싱 추가 기능 아이콘](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>조직에 대한 추가 기능 사용

> [!NOTE]
> 추가 기능을 조직에 표시하는 데 최대 12시간이 걸릴 수 있습니다.

1. Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다. 추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**

2. 페이지 **맨** 위에 있는 추가 기능 배포를 선택하고 다음 을 **선택합니다.**

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 새 **추가 기능** 배포 플라이아웃이 나타나면 정보를 검토하고 다음을 **클릭합니다.**

4. 다음 페이지에서 **스토어에서 선택을 클릭합니다.**

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

5. 나타나는 **추가 기능** 선택 페이지에서 검색 상자를 **클릭하고** 피싱 **보고를** 입력한 다음 검색 **검색** 아이콘 을 ![ ](../../media/search-icon.png) 클릭합니다. 결과 목록에서 피싱 **보고를 찾은** 다음 추가 를 **클릭합니다.**

6. 나타나는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 다음 계속을 **클릭합니다.**

7. 나타나는 **추가 기능 구성** 페이지에서 다음 설정을 구성합니다.

   - **할당된 사용자:** 다음 값 중 하나를 선택합니다.

     - **모든** 사용자(기본값)
     - **특정 사용자/그룹**
     - **저뿐이에요**

   - **배포 방법:** 다음 값 중 하나를 선택합니다.

     - **고정(기본값)**: 추가 기능은 지정된 사용자에게 자동으로 배포되며 제거할 수 없습니다.
     - **사용** 가능: 사용자는 홈 추가  기능 추가 기능 관리자가 관리하는 에서 추가 기능을 설치할 \>  \> **수 있습니다.**
     - **선택** 사항: 추가 기능을 지정된 사용자에게 자동으로 배포하지만 제거를 선택할 수 있습니다.

   완료되면 배포를 **클릭합니다.**

8. 보고서 **피싱** 배포 페이지에 나타나는 진행률 보고서와 추가 기능 배포 확인이 표시됩니다. 정보를 읽은 후 다음 을 **클릭합니다.**

9. 추가 기능 발표 **페이지가** 나타나면 정보를 검토하고 닫기 를 **클릭합니다.**

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>피싱 보고 추가 기능 설정 검토 또는 편집

1. Microsoft 365 관리 센터에서 의 설정  추가 기능 페이지로 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 이동합니다. 추가 기능 페이지가  없는 경우 통합 앱  페이지 맨 위에 있는 설정 통합 앱 추가 기능 \>  \>  **링크로 이동합니다.**

2. 피싱 **보고 추가** 기능을 찾아 선택합니다.

3. 조직에 **적합한** 설정이 나타나는 피싱 보고서 편집 플라이아웃에서 설정을 검토하고 편집합니다. 작업을 마쳤으면 **저장** 을 클릭합니다.

## <a name="view-and-review-reported-messages"></a>보고된 메시지 보기 및 검토

사용자가 Microsoft에 보고하는 메시지를 검토할 수 있는 옵션은 다음과 같습니다.

- 관리 제출 포털을 사용하세요. 자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)

- 메일 흐름 규칙(전송 규칙)을 만들어 보고된 메시지의 복사본을 전송합니다. 자세한 내용은 메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고하는 것을 [참조하세요.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)