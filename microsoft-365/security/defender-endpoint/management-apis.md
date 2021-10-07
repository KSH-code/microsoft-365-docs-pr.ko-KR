---
title: 관리 및 API 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 관리 도구 및 API 범주에 대해 자세히 알아보시고
keywords: 등록, api, siem, rbac, 액세스, 포털, 통합, 조사, 응답, 엔터티, 엔터티, 사용자 컨텍스트, 응용 프로그램 컨텍스트, 스트리밍
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 196c517c20e80b753bf6065c1c4e3014c0e16638
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154782"
---
# <a name="overview-of-management-and-apis"></a>관리 및 API 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)


Endpoint용 Defender는 고객이 플랫폼을 쉽게 채택할 수 있도록 다양한 옵션을 지원합니다.

고객 환경과 구조가 다를 수 있습니다. 끝점용 Defender는 다양한 고객 요구 사항에 맞게 유연성과 세분화된 제어를 통해 만들어졌습니다.

## <a name="endpoint-onboarding-and-portal-access"></a>끝점 온보드 및 포털 액세스

장치 온보딩은 클라이언트 Microsoft Endpoint Manager Microsoft Intune 및 서버 장치용 Azure Defender에 완전히 통합되어 구성, 배포 및 모니터링에 대한 완전한 종단 간 환경을 제공합니다. 또한 Endpoint용 Microsoft Defender는 그룹 정책 및 장치 관리에 사용되는 기타 타사 도구를 지원합니다.

끝점용 Defender는 포털에 액세스할 수 있는 사용자가 RBAC(역할 기반 액세스 제어)의 유연성을 통해 보고 할 수 있는 작업을 세분화하여 제어할 수 있도록 합니다. RBAC 모델은 모든 보안 팀 구조를 지원합니다.

- 전역으로 분산된 조직 및 보안 팀
- 계층 모델 보안 운영 팀
- 단일 중앙 집중식 전역 보안 운영 팀을 통해 완전히 구분된 부서

## <a name="available-apis"></a>사용 가능한 API

끝점용 Microsoft Defender 솔루션은 통합 준비가 완료된 플랫폼을 토로합니다.

Endpoint용 Defender는 프로그래밍 API 집합을 통해 많은 데이터와 작업을 노출합니다. 이러한 API를 통해 워크플로를 자동화하고 끝점용 Defender 기능을 기반으로 혁신할 수 있습니다.

![끝점용 Microsoft Defender의 사용 가능한 API 및 통합 이미지.](images/mdatp-apis.png)

끝점용 Defender API는 다음 세 가지로 그룹화할 수 있습니다.

- 끝점 API용 Microsoft Defender
- 원시 데이터 스트리밍 API
- SIEM 통합

## <a name="microsoft-defender-for-endpoint-apis"></a>끝점 API용 Microsoft Defender

Endpoint용 Defender는 사용자 또는 SaaS 응용 프로그램의 컨텍스트에서 액세스를 허용하는 표준 Azure AD 기반 인증 및 권한 부여 모델을 통해 노출되는 구조화되어 명확하며 사용하기 쉬운 모델의 데이터와 기능을 노출하는 계층화된 API 모델을 제공합니다. API 모델은 엔터티와 기능을 일관된 형태로 표시하도록 디자인되었습니다.

끝점 API용 Defender에 대한 간략한 개요는 이 비디오를 시청하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

조사 **API는** 계산된 또는 '프로필된' 엔터티(예: 장치, 사용자 및 파일)와 일반적으로 엔터티와 관련된 동작을 설명하는 불연결 이벤트(예: 프로세스 생성 및 파일 만들기)를 노출하여 쿼리 기반 데이터에 대한 액세스를 허용하는 조사 인터페이스를 통해 데이터에 액세스할 수 있도록 하는 엔드포인트용 Defender의 풍부한 기능을 노출합니다. 자세한 내용은 지원되는 [API를 참조하세요.](exposed-apis-list.md)

응답 **API는** 서비스 및 장치에서 작업을 수행할 수 있는 기능을 노출하여 고객이 표시기를 검색하고, 설정, 경고 상태를 관리하고, 장치에서 프로그래밍식으로 장치 격리, 파일 격리 등의 응답 작업을 수행할 수 있도록 합니다.

## <a name="raw-data-streaming-api"></a>원시 데이터 스트리밍 API

Endpoint 원시 데이터 스트리밍 API에 대한 Defender는 고객이 단일 데이터 스트림 내에서 발생할 때 인스턴스에서 실시간 이벤트 및 경고를 전달할 수 있도록 하여 짧은 대기 시간, 높은 처리률 전달 메커니즘을 제공합니다.

장기 데이터 보존을 위해 Endpoint용 Defender 이벤트 정보는 Azure 저장소에 직접 푸시되거나 시각화 서비스 또는 추가 데이터 처리 엔진에서 사용할 수 있도록 Azure 이벤트 허브로 푸시됩니다.

자세한 내용은 원시 데이터 스트리밍 [API 를 참조하세요.](raw-data-export.md)

새로운 Microsoft 365 Defender 스트리밍 API에는 장치 이벤트와 함께 전자 메일 및 경고 이벤트가 포함됩니다.
자세한 내용은 스트리밍 [API Microsoft 365 Defender 참조하세요.](../defender/streaming-api.md)

## <a name="siem-api"></a>SIEM API

SIEM(보안 정보 및 이벤트 관리) 통합을 사용하도록 설정하면 SIEM 솔루션을 Microsoft Defender 보안 센터 검색 REST API에 직접 연결하여 검색된 검색을 수집할 수 있습니다. 이렇게 하면 미리 채워진 값이 포함된 SIEM 커넥터 액세스 세부 정보 섹션이 활성화되어 응용 프로그램이 Azure Active Directory(Azure AD) 테넌트에 만들어집니다. 자세한 내용은 [SIEM 통합을 참조하세요.](enable-siem-integration.md)

## <a name="related-topics"></a>관련 항목

- [엔드포인트용 Microsoft Defender API에 액세스](apis-intro.md) 
- [지원되는 API](exposed-apis-list.md)
- [기술 파트너 기회](partner-integration.md)