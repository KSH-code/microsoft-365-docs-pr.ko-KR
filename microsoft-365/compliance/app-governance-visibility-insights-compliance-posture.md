---
title: 앱 규정 준수 상태 확인
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 앱 규정 준수 상태를 확인합니다.
ms.openlocfilehash: 4cc54e5ea0fdaf0a8a196b90b09e2e8be970c7c1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190019"
---
# <a name="determine-your-app-compliance-posture"></a>앱 규정 준수 상태 확인

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 앱 거버넌스를 사용하면 Microsoft 365 규정 준수 센터 앱 거버넌스 개요 페이지에서 타사 앱의 규정 준수 상태와 Microsoft 365 테넌트에서의 데이터 액세스를 신속하게 평가할 수 있습니다.

![Microsoft 365 준수 센터의 앱 거버넌스 개요 페이지.](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> 앱 거버넌스 데이터를 보려면 로그인 계정에 [관리자 역할](app-governance-get-started.md#administrator-roles) 중 하나가 부여되어야 합니다.
>

이 페이지에서 다음을 확인할 수 있습니다.

- Microsoft Graph API를 사용하는 OAuth 지원 앱의 경우 다음을 확인할 수 있습니다.

  - 사용자의 테넌트에 속한 수
  - 과도한 권한을 갖은 수
  - 높은 권한을 갖은 계정 수

  이 정보를 통해 권한이 과도하게 부여된 높은 권한의 앱을 통해 조직에 대한 위험 수준을 결정할 수 있습니다.

- 경고의 경우 다음을 확인할 수 있습니다.

  - 테넌트가 보유한 활성 경고 수
  - 앱 거버넌스 검색(**위협 경고**)을 기반으로 하는 경고 수
  - 적용된 앱 정책을 기반으로 하는 경고 수(**정책 경고**)
  - 10개의 최신 경고

  이 정보에서 경고가 생성되는 빈도와 검색된 경고 및 정책 기반 경고의 상대적 수를 확인할 수 있습니다.

- 데이터 및 리소스 액세스의 경우:

  - 현재 및 이전 3개월간 Graph API를 통해 테넌트의 앱에서 액세스한 총 데이터입니다. (현재 메일 및 파일 업로드와 다운로드 사용량만 포함)
  - 현재 및 이전 3개월간의 데이터 사용량을 리소스 종류별로 구분한 것입니다. (현재 메일 및 파일 업로드와 다운로드 사용량만 포함)

  이 정보로 Microsoft 365 테넌트에서 데이터 액세스가 비정상적으로 급증했는지 확인할 수 있습니다.
