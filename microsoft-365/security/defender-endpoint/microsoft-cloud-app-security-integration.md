---
title: Microsoft Cloud App Security 통합 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender는 모든 Cloud App Security 네트워킹 활동을 전달하여 앱과 통합됩니다.
keywords: 클라우드, 앱, 네트워킹, 가시성, 사용
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5d00c95323f0c2cebb030fd454df0073588ed39f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213615"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security용 Defender 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security)는 클라우드에 저장된 데이터에 대한 규정 준수 요구 사항을 적용하면서 클라우드 앱에 대한 액세스를 제어하고 제한할 수 있도록 하여 클라우드 앱 및 서비스에 대한 가시성을 제공하는 포괄적인 솔루션입니다. 자세한 내용은 를 [Cloud App Security.](/cloud-app-security/what-is-cloud-app-security)

> [!NOTE]
> 이 기능은 버전 1809 [이상을](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) 실행하는 Enterprise Mobility + Security E5 라이선스와 함께 사용할 Windows 10 있습니다.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint 및 Cloud App Security 통합

Cloud App Security 검색은 엔터프라이즈 방화벽 및 프록시 서버에서 클라우드 트래픽 로그로 전달되는 로그에 의존합니다. 끝점용 Microsoft Defender는 모든 Cloud App Security 네트워킹 활동을 수집 및 전달하여 클라우드 앱 사용에 대해 최고의 가시성을 제공합니다. 모니터링 기능은 장치에 기본 제공되어 네트워크 활동에 대한 전체 범위를 제공합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

통합을 통해 기존 검색에 다음과 같은 주요 Cloud App Security 있습니다.

- 모든 곳에서 사용 가능 - 네트워크 활동은 끝점에서 직접 수집하기 때문에 엔터프라이즈 방화벽 또는 프록시 서버를 통해 라우팅되는 트래픽에 더 이상 종속되지 않고 장치가 회사 네트워크의 설정 또는 해제된 모든 곳에서 사용할 수 있습니다.

- 구성이 필요 없는 기본 제공 작업 - 클라우드 트래픽 로그를 방화벽 Cloud App Security 프록시 서버 구성이 필요합니다. 끝점용 Defender 및 Cloud App Security 통합에서는 구성이 필요하지 않습니다. 설정에서 Microsoft Defender 보안 센터 켜면 됩니다.\

- 디바이스 컨텍스트 - 클라우드 트래픽 로그에 장치 컨텍스트가 없습니다. 끝점 네트워크 활동에 대한 Defender는 장치 컨텍스트(클라우드 앱에 액세스한 장치)로 보고됩니다. 따라서 네트워크 활동이 수행된(사용자) 외에 네트워크 활동이 수행된 위치를 정확하게 이해할 수 있습니다.

클라우드 검색에 대한 자세한 내용은 검색된 앱 [작업을 참조하세요.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>관련 항목

- [Microsoft Cloud App Security 통합 구성](microsoft-cloud-app-security-config.md)
