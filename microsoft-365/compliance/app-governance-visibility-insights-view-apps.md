---
title: 앱 보기
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 앱을 봅니다.
ms.openlocfilehash: d4de5916fc900c0a45996e3ad1dcb816cc5f94aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168881"
---
# <a name="view-your-apps"></a>앱 보기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 앱 거버넌스를 사용하면 사용자의 테넌트의 Microsoft 365 앱에 대한 심층적인 인사이트를 빠르게 얻을 수 있습니다. 예를 들어 다음을 볼 수 있습니다.

- 관련 앱 메타데이터 및 사용량 현황 데이터와 함께 Microsoft Graph API를 사용하는 테넌트 내의 OAuth 지원 앱 목록입니다.
- 목록에서 앱을 선택하여 심층적인 인사이트와 정보를 포함하는 앱 세부 정보입니다.

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>테넌트의 모든 앱 목록 가져오기

테넌트에서 앱에 대한 요약을 보려면 **Microsoft 365 규정 준수 센터 > 앱 거버넌스 > 앱** 으로 이동하세요.

![Microsoft 365 규정 준수 센터의 MAPG 앱 요약 페이지.](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> 앱 거버넌스 데이터를 보려면 로그인 계정에 [관리자 역할](app-governance-get-started.md#administrator-roles) 중 하나가 부여되어야 합니다.
>

앱 목록과 다음 정보가 표시됩니다.

- 앱 이름
- 게시자
- M365 인증

  앱이 Microsoft 기술과 호환되는지, Cloud App Security 모범 사례를 준수하며, Microsoft에서 지원하는지 여부를 나타냅니다.

- 마지막으로 수정한 날짜

  해당 날짜가 앱이 마지막으로 수정된 날짜보다 최신인 경우 클라이언트에 앱 거버넌스가 설치된 날짜를 표시합니다.

- 설치한 날짜
- 권한 수준
- 사용자 수
- 데이터 액세스

  마지막 날의 테넌트에서 앱의 데이터 업로드 및 다운로드 합계와 그 전 날의 변경 내용입니다.

앱 거버넌스는 기본적으로 **앱 이름** 순으로 앱 목록을 정렬합니다. 목록을 다른 앱 특성별로 정렬하려면 특성 이름을 선택합니다.

**검색** 을 선택하여 앱의 이름을 검색할 수도 있습니다.

## <a name="getting-detailed-information-on-an-app"></a>앱에 대한 자세한 정보 가져오기

테넌트의 특정 앱에 대한 자세한 내용은 **Microsoft 365 규정 준수 센터 > 앱 거버넌스 > 앱 페이지 > *앱 이름***으로 이동하세요.

![Microsoft 365 규정 준수 센터의 앱 거버넌스 앱 세부 정보 창.](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

앱 세부 정보 창은 다음 탭에 관한 추가 정보를 제공합니다.

| 탭 이름 | 설명 |
|:-------|:-----|
| 세부 정보 | 앱에서 처음 동의한 날짜 및 앱 ID와 같은 추가 데이터를 확인합니다. Azure AD에 등록된 앱의 속성을 보려면 **Azure AD의 앱 보기** 를 선택합니다. |
| 사용 현황 |테넌트의 앱에서 액세스하는 데이터를 확인하고 SharePoint 및 Exchange 리소스에 대한 데이터 사용량을 표시합니다. |
| 사용자 | 앱을 사용하는 사용자 목록, 우선 순위 계정 여부와 다운로드 및 업로드된 데이터 양을 확인합니다. |
| 사용 권한 | 앱에 부여된 사용 권한 및 앱이 사용하는 사용 권한과 특정 사용 권한 목록의 요약을 확인하세요. 자세한 내용은 [Microsoft Graph 사용 권한 참조](/graph/permissions-reference)를 참조하세요. |
|||

활성화된 앱의 경우 **앱 비활성화** 컨트롤을 사용하여 선택된 앱을 비활성화할 수 있고 **앱 활성화** 컨트롤을 사용하여 비활성화된 앱을 사용하도록 설정하는 기능도 있습니다. 이러한 작업을 수행하려면 다음 관리자 역할이 필요합니다.

- 규정 준수 관리자
- 전역 관리자
- 보안 관리자
- 보안 운영자

## <a name="next-step"></a>다음 단계

[전반적인 앱 규정 준수 상태를 결정합니다.](app-governance-visibility-insights-compliance-posture.md)
