---
title: 조직에 대한 Microsoft 피드백 관리
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 사용자가 Microsoft 제품에 대해 Microsoft에 보낼 수 있는 피드백을 관리합니다.
ms.openlocfilehash: 7d6d607182a546e869a9f92e84adfa31f7e02a26
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187212"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>조직에 대한 Microsoft 피드백 관리

Microsoft 365 조직의 관리자는 Microsoft 365 응용 프로그램을 사용할 때 사용자의 피드백 수집 및 고객 참여 환경을 관리하는 데 도움이 되는 몇 가지 Microsoft 365 있습니다. 이러한 각 정책에 대해 조직의 기존 Azure Active Directory 그룹을 만들고 사용할 수 있습니다. 이러한들을 사용하여 조직의 여러 부서가 Microsoft에 피드백을 보낼 수 있는 방법을 제어할 수 있습니다. Microsoft는 고객이 제출한 모든 피드백을 검토하고 이 피드백을 사용하여 제품을 개선합니다. 피드백 환경을 으로  유지하면 사용 중이던 Microsoft 제품에 대해 사용자가 말하는 것을 볼 수 있습니다. 사용자로부터 수집하는 피드백은 에서 곧 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터.</a>

피드백 유형 및 Microsoft에서 사용자 피드백을 사용하는 방법에 대한 자세한 내용은 [조직에 대한 Microsoft 피드백에 대해 자세히 보기를 참조합니다.](../misc/feedback-user-control.md)

아래 표에는 아래 피드백 정책 표에 표시된 피드백 정책에 현재 연결된 앱 및 서비스가 나와 있습니다. 스크린샷 예제는 아래 표를 참조하세요.

|**앱 & 서비스**|**제품 내 피드백** <br> |**제품 내 설문 조사** <br> |**메타데이터 컬렉션** <br> |**고객 참여** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|예|예|예|예|
|**Excel**|예|예|예|예|
|**Office.com**|출시 예정|출시 예정|출시 예정|출시 예정|
|**OneNote**|예|예|예|예|
|**OneDrive**|[일부 설정은 현재 다른 컨트롤에 의해 관리됩니다.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|출시 예정|출시 예정|출시 예정|출시 예정|
|**PowerPoint**|예|예|예|예|
|**Project**|출시 예정|출시 예정|출시 예정|출시 예정|
|**게시자**|예|예|예|예|
|**SharePoint**|[일부 설정은 현재 다른 컨트롤에 의해 관리됩니다.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[일부 설정은 현재 다른 컨트롤에 의해 관리됩니다.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|예|예|예|예|
|**Visio**|예|예|예|예|
|**Yammer**|예|예|예|예|

[제품 내 설문 조사 및 피드백의 몇 가지 예는 여기를 참조하세요.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**메타데이터 컬렉션**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Screenshot: Feedback page showing metadata example":::

**고객 참여**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Screenshot: In-product customer research question example":::

## <a name="before-you-begin"></a>시작하기 전에

이러한 정책을 사용하려면 장치가 최소 빌드 번호에 있어야 합니다. 자세한 내용은 아래 표를 참조하세요.

|**빌드 #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|제품 내 피드백|16.0.13328 이상|2.42 이상|16.0.13328 이상|16.42 이상|공개적으로 사용 가능|
|제품 내 설문 조사|16.0.13328 이상|2.42 이상|16.0.13426 이상|16.42 이상|보류 중인 출시|
|메타데이터 컬렉션|16.0.13328 이상|2.42 이상|16.0.13328 이상|16.42 이상|공개적으로 사용 가능|
|고객 참여|16.0.13328 이상|2.42 이상|16.0.13426 이상|16.42 이상|보류 중인 출시|

## <a name="specific-policies-you-can-configure"></a>구성할 수 있는 특정 정책

### <a name="feedback-policies"></a>피드백 정책

|**정책 이름**|**기본 상태**|**컨트롤 요약**|
|:-----|:-----|:-----|
|사용자가 Microsoft에 피드백을 제출할 수 있도록 허용|설정|응용 프로그램 전반에 걸쳐 피드백 진입점을 제어합니다.|
|사용자가 Microsoft에서 제품 내 설문 조사를 받고 응답할 수 있도록 허용|설정|제품 내에서 설문 조사 프롬프트 제어|
|사용자가 Microsoft에 피드백을 제출할 때 스크린샷 및 첨부 파일을 포함하도록 허용|해제|사용자가 피드백/설문 조사를 통해 제출하도록 결정할 수 있는 메타데이터 결정|
|사용자가 제출한 피드백에 대해 Microsoft에서 후속 업데이트 허용|해제|사용자가 피드백/설문 조사와 연락처 정보를 공유할 수 있는지 여부를 결정|
|Microsoft에 피드백을 제출할 때 사용자가 로그 파일 및 콘텐츠 샘플을 포함하도록 허용|해제|사용자가 피드백/설문 조사를 통해 제출하도록 결정할 수 있는 메타데이터 결정|

## <a name="configure-policies"></a>정책 구성

1. 으로 [https://config.office.com](https://config.office.com) 이동하여 로그인합니다.
1. 사용자 **지정을 선택한** 다음 **정책 관리를 선택합니다.**
1. **만들기** 를 선택합니다.
1. 이름 **및 설명을** **입력합니다.**
1. 구성할 Azure Active Directory 그룹을 선택하십시오.
1. 피드백 및 **설문 조사를** **검색합니다.**
1. 나열된 각 정책에 대해 원하는 값을 설정합니다.

자세한 내용은 클라우드 정책 서비스 Office [개요를 참조하세요.](/deployoffice/overview-office-cloud-policy-service)

이러한 정책 설정은 그룹 정책을 사용하는 경우도 사용할 수 있습니다. 이러한 정책 설정을 사용하려면 2021년 3월 22일 출시된 관리 템플릿 [파일(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)버전 5146.1000 이상을 다운로드합니다.

이러한 정책 설정은 사용자 구성 -> 정책 -> 관리 템플릿 -> Microsoft Office -> 개인 정보 -> 보안 센터에서 찾을 수 있습니다.

> [!NOTE]
> 클라이언트 응용 프로그램을 업데이트하는 데 몇 시간이 소요됩니다.
