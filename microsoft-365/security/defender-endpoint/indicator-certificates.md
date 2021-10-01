---
title: 인증서를 기반으로 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 인증서를 기반으로 표시기를 만들 수 있습니다.
keywords: ioc, 인증서, 인증서, 관리, 허용, 차단, 차단, 클린, 악성, 파일 해시, ip 주소, URL, 도메인
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b471bcfa1c4a42ddf5c49c2a0bc2129c99fd9297
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60043350"
---
# <a name="create-indicators-based-on-certificates"></a>인증서를 기반으로 표시기 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

인증서에 대한 표시기를 만들 수 있습니다. 몇 가지 일반적인 사용 사례는 다음과 같습니다.

- 공격 표면 감소 규칙 및 제어된 [](attack-surface-reduction.md) 폴더 액세스와 [](controlled-folders.md) 같은 차단 기술을 배포해야 하지만 허용 목록에 인증서를 추가하여 서명된 응용 프로그램의 동작을 허용해야 하는 시나리오입니다.
- 조직 전체에서 서명된 특정 응용 프로그램의 사용을 차단합니다. 응용 프로그램의 인증서를 차단하는 표시기를 만들면 Windows Defender AV는 파일 실행(차단 및 수정)을 방지하고 자동화된 조사 및 수정이 동일하게 실행됩니다.

## <a name="before-you-begin"></a>시작하기 전에

인증서에 대한 표시기를 만들기 전에 다음 요구 사항을 이해하는 것이 중요합니다.

- 이 기능은 조직에서 클라우드 기반 보호를 Windows Defender 바이러스 백신 경우 사용할 수 있습니다. 자세한 내용은 클라우드 기반 보호 [관리를 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- 맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.
- Windows 10, 버전 1703 이상, Windows 서버 2016, 2019 및 Windows Server 2022의 컴퓨터에서 지원됩니다.
- 바이러스 및 위협 방지 정의는 최신해야 합니다.
- 이 기능은 현재 를 입력할 수 있습니다. CER 또는 . PEM 파일 확장명입니다.

> [!IMPORTANT]
>
> - 유효한 리프 인증서는 유효한 인증 경로가 있으며 Microsoft에서 신뢰하는 루트 CA(인증 기관)에 연결되어야 하는 서명 인증서입니다. 또는 클라이언트가 신뢰하는 한 사용자 지정(자체 서명된) 인증서를 사용할 수 있습니다(루트 CA 인증서는 로컬 컴퓨터 '신뢰할 수 있는 루트 인증 기관'에 설치됩니다.
> - 허용/차단 인증서 IOC의 자식 또는 부모는 IoC 허용/차단 기능에 포함되지 않습니다. 리프 인증서만 지원됩니다.
> - Microsoft 서명된 인증서는 차단할 수 없습니다.

## <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>설정 페이지에서 인증서에 대한 표시기를 만드십시오.

> [!IMPORTANT]
> 인증서 IoC를 만들고 제거하는 데 최대 3시간이 걸릴 수 있습니다.

1. 탐색 창에서 **끝점 설정(규칙** 아래)를 \>  \>  **선택합니다.**

2. 표시기 **추가를 선택합니다.**

3. 다음 세부 정보를 지정합니다.
   - Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.
   - 작업 - 수행될 작업을 지정하고 설명을 입력합니다.
   - 범위 - 컴퓨터 그룹의 범위를 정의합니다.

4. 요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**

## <a name="related-topics"></a>관련 항목

- [지표 만들기](manage-indicators.md)
- [파일에 대한 지표 만들기](indicator-file.md)
- [IP 및 URL/도메인에 대한 지표 만들기](indicator-ip-domain.md)
- [지표 관리](indicator-manage.md)
