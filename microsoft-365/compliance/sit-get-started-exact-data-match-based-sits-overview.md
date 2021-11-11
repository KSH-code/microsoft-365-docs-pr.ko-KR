---
title: 정확한 데이터 일치 기반 중요한 정보 유형 시작
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 중요한 정보 유형 기반의 정확한 데이터 일치 만들기를 시작하세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3621ccdedb5966ae7c70e549c5f0538143df0248
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914870"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>정확한 데이터 일치 기반 중요한 정보 유형 시작

EDM(정확한 데이터 일치) 기반의 SIT(중요한 정보 유형)를 만들고 사용할 수 있도록 하는 과정은 여러 단계로 진행됩니다. 데이터 손실 방지 정책, eDiscovery 및 특정 콘텐츠 거버넌스 작업에서 사용할 수 있습니다. 이 문서에서는 워크플로 및 각 단계에 대한 절차에 대한 링크를 간략하게 설명합니다.

## <a name="before-you-begin"></a>시작하기 전에

다음 문서의 개념과 용어를 잘 알고 있습니다.

- [중요한 정보 유형에 대해 알아보기](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

이 문서에 설명된 작업을 수행하려면 전역 관리자, 준수 관리자 또는 Exchange Online 관리자여야 합니다. DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.

전체 라이선스 [정보는 데이터 손실](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) 방지 서비스 설명을 참조하세요.

## <a name="portal-links-for-your-subscription"></a>구독을 위한 포털 링크

|포털|전세계/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 보안 센터|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 규정 준수 센터|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>워크플로 한 눈에 보기

![정확한 데이터 일치 워크플로 단계](..\media\swimlane_edm_process.png)


|단계|필요한 사항|
|---|---|
|[1단계: 중요한 정보 유형에 따라 정확한 데이터 일치에 대한 원본 데이터 내보내기](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 중요한 데이터에 대한 읽기 액세스 권한|
|[2단계: 중요한 정보 유형 기반의 정확한 데이터 일치에 대한 스마마 만들기](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- 2013에서 중요한 정보 유형 마법사에 Microsoft 365 관리 센터 </br>- 보안 및 [Microsoft 365 관리 센터 PowerShell을 & 액세스](/powershell/exchange/connect-to-scc-powershell) |
|[3단계: 중요한 정보 유형과 일치하는 정확한 데이터용 중요한 정보 원본 테이블 해시 및 업로드](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- 사용자 지정 보안 그룹 및 사용자 계정 </br>- **한 컴퓨터에서** 해시 및 업로드: 직접 인터넷에 액세스할 수 있는 컴퓨터에 대한 로컬 관리자 액세스 및 EDM 관리자 업로드 에이전트 </br>- **별도의** 컴퓨터에서 해시 및 업로드: 직접 인터넷에 액세스할 수 있는 컴퓨터에 대한 로컬 관리자 액세스 및 EDM 업로드 에이전트를 호스트하고, 중요한 정보 원본 테이블을 해시하기 위해 EDM 업로드 에이전트를 호스트하는 보안 컴퓨터에 대한 로컬 관리자 액세스 </br>- 중요한 정보 원본 테이블 파일에 대한 읽기 액세스 </br> schema 파일 |
|[4단계: 정확한 데이터 일치 중요한 정보 유형/규칙 패키지 만들기](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- Microsoft 365 규정 준수 센터에 대한 액세스 |
|[중요한 정보 유형과 일치하는 정확한 데이터 테스트](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - Microsoft 365 규정 준수 센터에 대한 액세스

## <a name="see-also"></a>참고 항목

- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [정확한 데이터 일치 기반의 중요한 정보 유형에 대한 원본 데이터 내보내기](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
