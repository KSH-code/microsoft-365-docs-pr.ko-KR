---
title: Microsoft 개인 정보 관리(미리 보기) 시작
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: 조직에 대한 개인 정보 관리를 설정하고, 역할 및 사용 권한을 설정하고, 중요한 설정을 구성하는 방법을 배워야 합니다.
ms.openlocfilehash: 229d4bec78424858cd7034c8953313f8593e90e3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186027"
---
# <a name="get-started-with-privacy-management-preview"></a>개인 정보 관리 시작(미리 보기)

개인 정보 관리는 현재 공개 미리 보기에서 사용할 수 있습니다. 조직에 대한 액세스를 설정하고 데이터 평가를 시작하는 방법을 배워야 합니다.

## <a name="who-can-access-privacy-management"></a>Who 개인 정보 관리에 액세스할 수 있습니다.

개인 정보 관리의 공개 미리 보기는 조직 내에서 사용할 수 Microsoft 365 규정 준수 센터 E1, E3 및 E5 엔터프라이즈 라이선스가 있는 조직에서 Office 365 Microsoft 365. 개인 정보 관리가 일반 공급으로 이동하면 공개 미리 보기를 사용한 조직은 새 라이선스를 획득해야 합니다.

자세한 라이선싱에 대한 지침은 [보안 및 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.

> [!Note]
> 개인 정보 관리의 공개 미리 보기는 미국 정부 Community(GCC) 보통, GCC 또는 DoD(국방부) 고객은 사용할 수 없습니다.

## <a name="set-up-privacy-management"></a>개인 정보 관리 설정

개인 정보 관리를 시작하기 위해 먼저 무료 평가판 라이선스를 얻습니다. 그런 다음 로그인하고, 사용자에게 사용 권한을 할당하고, 설정을 검토하고, 개인 정보 관리의 기능을 사용할 수 있습니다.

### <a name="get-free-trial-license"></a>무료 평가판 라이선스 다운로드

공개 미리 보기를 시작하려면 전역 관리자가 관리 센터에서 무료 개인 정보 관리 평가판 라이선스를 [얻을 수 있습니다.](https://aka.ms/purchasem365privacy) 시작하려면 "평가판 시작"을 선택합니다. 라이선스는 한 달 동안 지속됩니다. 공개 미리 보기 중에 필요한 경우 비용으로 갱신할 수 있습니다.

구독을 얻은 후 정품 인증을 위해 최대 30분을 허용합니다. 그런 다음 규정 준수 센터의 개인 정보 관리로 돌아와서 시작할 수 있습니다.

개인 정보 관리를 처음 열면 약관 및 개인 데이터 평가 프로세스(자세한 정보)에 동의하는지 확인하는[것이 요청됩니다.](privacy-management.md#where-privacy-management-identifies-personal-data) 계속하기 전에 제공된 링크를 전체 검토할 수 있습니다. 동의하면 개인 정보 관리가 조직의 데이터에 대한 인사이트 제공을 시작하기까지 최대 24시간이 걸릴 수 있습니다.

개인 정보 관리 사용 약관에 대한 구독 또는 동의를 얻기 위해 필요한 역할을 보유하지 않는 경우 전역 관리자에게 지원을 요청하라는 메시지가 표시됩니다.

### <a name="set-user-permissions-and-assign-roles"></a>사용자 권한 설정 및 역할 할당

개인 정보 관리는 RBAC(역할 기반 액세스 제어) 사용 권한 모델을 사용 합니다. 역할이 할당된 사용자만 개인 정보 관리에 액세스할 수 있으며 각 사용자가 허용하는 작업은 역할 유형에 따라 제한됩니다.

개인 정보 관리를 처음 사용할 때 전역 관리자가 로그인하고 준수 센터에서 사용자 권한을 설정하는 것이 좋습니다. 빠른 시작을 위해 개인 정보 관리 역할 그룹에는 개인 정보 관리의 모든 기능에 액세스할 수 있는 권한이 있습니다. 이 그룹은 개인 정보 관리 솔루션 내에서 동일한 개인이 모든 업무를 수행할 수 있는 조직에 적합할 수 있습니다. 다른 개인 정보 보호 역할을 사용하면 보다 세부적인 제어를 수행하고 선택한 기능이나 기능에 사용자를 할당할 수 있습니다.

역할 그룹 및 액세스 권한을 부여하는 방법에 대한 자세한 내용은 사용자 권한 설정 및 역할 [할당을 참조합니다.](privacy-management-permissions.md)

### <a name="manage-settings"></a>설정 관리

개인 설정 페이지의 오른쪽 위 모서리에 있는 기어 휠을 통해 액세스할 수 있습니다. 개인 정보 관리 관리자는 이 기능을 통해 개인 정보 관리 전반에 걸쳐 중요한 속성(예를 들어, 비동기화, 전자 메일 알림 등)을 구성할 수 있습니다.

시작하기 전에 기본 구성을 검토하고 원하는 조정을 할 수 있습니다. 옵션에 대한 자세한 내용은 개인 정보 관리 설정 [관리를 참조하세요.](privacy-management-settings.md)

## <a name="start-visualizing-your-data"></a>데이터 시각화 시작

개인 정보 관리에 로그인한 후 개요 페이지에 **도착합니다.** 이 페이지에서는 문제를 빠르게 파악하고, 위험 지표를 식별하고, 문제를 해결하기 위한 조치를 취할 수 있도록 Microsoft 365 환경에 저장된 개인 데이터에 대한 인사이트를 제공합니다. 개요는 등록 후 처음 24시간 내에 초기 정보를 채워야 합니다. 개인 정보 관리를 계속 사용할 때 개요 페이지가 새로 고쳐 현재 정보를 계속 제공합니다.

시간이 지날수록 데이터에 대한 추가  정보를 얻을 수 있도록 데이터 프로필 페이지에서는 더 많은 시각화 및 분석을 제공하고 지리적 위치 및 서비스로 조직의 데이터를 개 Microsoft 365 제공합니다.

이러한 페이지에 대한 자세한 내용은 데이터 찾기 및 [시각화를 참조하세요.](privacy-management-data-profile.md)

## <a name="start-managing-risks-with-default-policies"></a>기본 정책을 통해 위험 관리 시작

개인 정보 보호 관리는 데이터 평가를 시작하고 데이터 최소화, 데이터 과다 노출 및 데이터 전송을 위한 템플릿을 사용하여 기본 설정이 있는 세 가지 정책을 만들어 주요 위험 시나리오를 살펴보는 데 도움이 됩니다. 이러한 정책은 기본적으로 설정되지만 알림 메일 또는 수정 프롬프트를 자동으로 트리거하지는 않습니다. 초기 설정 후 정책을 만들고 사용자 지정할 수 있습니다. 자세한 내용은 정책 만들기 [및 관리를 참조합니다.](privacy-management-policies.md)

## <a name="get-started-with-subject-rights-requests"></a>주체 권한 요청 시작

개인 정보 보호 관리의 주체 권한 요청 솔루션은 저장하는 개인 데이터를 검토하거나 관리하려는 개인의 요청을 처리하는 데 도움이 될 수 있습니다. 이러한 기능 사용에 대한 자세한 내용은 주체 권한 요청 [관리를 참조합니다.](privacy-management-subject-rights-requests.md)
