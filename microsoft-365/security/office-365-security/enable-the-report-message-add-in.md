---
title: 보고서 메시지 추가 기능을 사용하도록 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 개별 사용자 또는 전체 조직에 대해 Outlook 및 웹용 Outlook용 보고서 메시지 추가 기능을 사용하도록 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826640"
---
# <a name="enable-the-report-message-add-in"></a>보고서 메시지 추가 기능을 사용하도록 설정

> [!NOTE]
> Exchange Online 사서함을 사용 하 고 Microsoft 365 조직의 관리자는 보안 도메인 준수 센터에서 제출 포털을 & 좋습니다. 자세한 내용은 [관리자 제출 사용을 참조하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출하세요.](admin-submission.md)

Outlook 및 웹용 Outlook(이전의 Outlook Web App)에 대한 보고서 메시지 추가 기능을 사용하면 사용자들이 가양성(잘못된 전자 메일로 표시) 또는 거짓 부정(잘못된 전자 메일이 허용된 경우)을 분석용으로 쉽게 보고할 수 있습니다. Microsoft는 이러한 제출을 사용하여 전자 메일 보호 기술의 효율성을 개선합니다.

예를 들어 다른 사용자가 피싱으로 많은 메시지를 보고한다고 가정해 보시기 바라고 가정해보시다. 보안 대시보드 및 기타 [보고서의 이 정보가](security-dashboard.md) 표시됩니다. 조직의 보안 팀은 이 정보를 피싱 방지 정책을 업데이트해야 할 수 있다는 명시로 사용할 수 있습니다. 또는 사용자가 보고서 메시지 추가 기능을 사용하여 정크 메일이 정크 메일로 플래그가 지정된 대량의 메시지를 보고하는 경우 조직의 보안 팀에서 스팸 방지 [정책을 조정해야 할 수도 있습니다.](configure-your-spam-filter-policies.md)

또한 조직에서 [Office 365 Advanced Threat Protection Plan 1 또는](office-365-atp.md) [Plan 2를](office-365-ti.md)사용하는 경우 보고서 메시지 추가 기능은 보안 정책을 검토하고 업데이트하는 데 사용할 수 있는 유용한 정보를 조직의 보안 팀에 제공합니다.

관리자는 조직의 보고서 메시지 추가 기능을 사용하도록 설정할 수 있고 개별 사용자가 자신을 위해 설치할 수 있습니다.

개별 사용자이면 보고서 메시지 추가 [기능을 자신을 위해 사용하도록 설정할 수 있습니다.](#get-the-report-message-add-in-for-yourself)

전역 관리자이거나 Exchange Online 관리자이고 Exchange가 OAuth 인증을 사용하도록 구성된 경우 조직에 대해 [보고서 메시지 추가 기능을 사용하도록 설정할 수 있습니다.](#get-and-enable-the-report-message-add-in-for-your-organization) 이제 보고서 메시지 추가 기능을 중앙 집중식 [배포를 통해 사용할 수 있습니다.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- 보고서 메시지 추가 기능은 대부분의 Microsoft 365 구독 및 다음 제품에서 작동합니다.

  - 웹용 Outlook
  - Outlook 2013 SP1 이상
  - Mac용 Outlook 2016
  - 엔터프라이즈용 Microsoft 365 앱에 포함된 Outlook

- 보고서 메시지 추가 기능은 온-프레미스 Exchange 조직의 사서함에 사용할 수 없습니다.

- 지정한 사서함으로 복사 또는 리디렉션하도록 보고된 메시지를 구성할 수 있습니다. 자세한 내용은 [Exchange Online에서 스팸 및 피싱 메시지의 사용자 전송을 위한 사서함 지정을 참조하세요.](user-submission.md)

- 보고서 메시지 추가 기능을 사용하려면 기존 웹 브라우저가 작동해야 합니다. 그러나 추가 기능을 사용할 수 없거나 예상대로 작동하지 않는 경우 다른 브라우저를 시도해 보세요.

- 조직 설치의 경우에는 조직에서 OAuth 인증을 사용하도록 구성해야 합니다. 자세한 내용은 [요약에서 추가 기능의 중앙 집중식 배포가 조직에서 작동하는지 확인하세요.](../../admin/manage/centralized-deployment-of-add-ins.md)

- 관리자는 Global admins 역할 그룹의 구성원이어야 합니다. 자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

## <a name="get-the-report-message-add-in-for-yourself"></a>자신을 위한 보고서 메시지 추가 기능 가져오기

1. Microsoft AppSource로 이동한 <https://appsource.microsoft.com/marketplace/apps> 후 보고서 메시지 추가 기능을 검색합니다. 보고서 메시지 추가 기능으로 직접 이동하려면 다음으로 <https://appsource.microsoft.com/product/office/wa104381180> 이동합니다.

2. 지금 **액세스를 클릭합니다.**

   ![보고 메시지 - 가져오기](../../media/ReportMessageGETITNOW.png)

3. 표시되는 대화 상자에서 사용 약관 및 개인 정보 취급 방침을 검토한 후 계속을 **클릭합니다.**

4. 회사 또는 학교 계정(비즈니스 용도) 또는 Microsoft 계정(개인용)을 사용하여 로그인합니다.

추가 기능이 설치되어 사용하도록 설정되면 다음 아이콘이 표시됩니다.

- Outlook에서 아이콘은 다음과 같습니다.

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- 웹용 Outlook에서 아이콘은 다음과 같이 표시됩니다.

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

추가 기능을 사용하는 방법에 대한 자세한 내용은 보고서 [메시지 추가 기능 사용을 참조하세요.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>조직용 보고서 메시지 추가 기능 받기 및 사용

> [!NOTE]
> 추가 기능이 조직에 나타나려면 최대 12시간이 걸릴 수 있습니다.

1. Microsoft 365 관리 센터에서 추가 **기능 & 페이지로** 이동한 다음 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 추가 기능 **배포를 클릭합니다.**

   ![Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 표시되는 새 **추가 기능 배포 플라이아웃에서** 정보를 검토한 후 다음을 **클릭합니다.**

3. 다음 페이지에서 Choose from the **Store(스토어에서 선택)을 클릭합니다.**

   ![새 추가 기능 페이지 배포](../../media/NewAddInScreen2.png)

4. **나타나는 추가 기능** 선택 페이지에서 보고서 메시지를 **입력하고**검색 아이콘을 **Search** **Search** ![ ](../../media/search-icon.png) 클릭합니다. 결과 목록에서 보고서 메시지를 찾은 **다음 추가를** **클릭합니다.**

   ![추가 기능 검색 결과 선택](../../media/NewAddInScreen3.png)

5. 표시되는 대화 상자에서 라이선스 및 개인 정보 보호 정보를 검토한 후 계속을 **클릭합니다.**

6. 추가 **기능 구성 페이지가** 나타나면 다음 설정을 구성합니다.

   - **할당된**사용자: 다음 값 중 하나를 선택합니다.

     - **모든** 사용자(기본값)
     - **특정 사용자/그룹**
     - **저뿐이에요**

   - **배포 방법:** 다음 값 중 하나를 선택합니다.

     - **고정됨(기본값):** 추가 기능이 지정된 사용자에게 자동으로 배포되며 사용자가 제거할 수 없습니다.
     - **사용**가능: 사용자가 홈 가져오기 추가 **기능에서** \> **관리자 관리를 통해 추가 기능을** \> **설치할 수 있습니다.**
     - **선택**사항 : 추가 기능이 지정된 사용자에게 자동으로 배포되지만 이를 제거하도록 선택할 수 있습니다.

   ![추가 기능 페이지 구성](../../media/configure-add-in.png)

   작업을 마치면 배포를 **클릭합니다.**

7. 보고서 **보고서 배포 페이지에** 표시되는 보고서, 추가 기능이 배포되었다는 확인 메시지가 표시됩니다. 정보를 확인한 후 다음을 **클릭합니다.**

   ![보고서 메시지 배포 페이지](../../media/deploy-report-message-page.png)

8. On the **Announce add-in** page that appears, and then click **Close.**

   ![추가 기능 페이지 알림](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>보고서 메시지 추가 기능을 사용하는 방법 알아보기

추가 기능이 할당된 사람은 다음 아이콘을 볼 수 있습니다.

- Outlook에서 아이콘은 다음과 같습니다.

  ![Outlook용 보고서 메시지 추가 기능 아이콘](../../media/OutlookReportMessageIcon.png)

- 웹용 Outlook에서 아이콘은 다음과 같이 표시됩니다.

  ![웹용 Outlook 보고서 메시지 추가 기능 아이콘](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

보고서 메시지 추가 기능에 대해 사용자에게 이를 보낼 때는 보고서 메시지 추가 [기능을 사용하기 위한 링크를 포함합니다.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>보고서 메시지 추가 기능에 대한 설정 검토 또는 편집

1. Microsoft 365 관리 센터에서 서비스 대시보드 **& 페이지로** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 이동합니다.

   ![새 Microsoft 365 관리 센터의 서비스 및 추가 기능 페이지](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 보고서 메시지 추가 **기능을 찾아** 선택합니다.

3. 표시되는 보고서 **메시지 플라이아웃에서** 해당 조직에 맞게 설정을 검토 및 편집합니다. 작업을 마쳤으면 **저장**을 클릭합니다.

   ![보고서 메시지 추가 기능 설정](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>보고된 메시지 보기 및 검토

사용자가 Microsoft에 보고한 메시지를 검토하려면 다음 옵션을 사용합니다.

- 관리자 제출 포털을 사용합니다. 자세한 내용은 [Microsoft에 대한 사용자 제출 보기를 참조하세요.](admin-submission.md#view-user-submissions-to-microsoft)

- 보고된 메시지의 복사본을 보낼 메일 흐름 규칙(전송 규칙이라고도 함)을 만듭니다. 자세한 내용은 메일 흐름 [규칙을 사용하여 사용자가 Microsoft에 보고한 내용을 확인합니다.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
