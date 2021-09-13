---
title: 기본 Microsoft 365 Lighthouse 배포
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스를 사용하는 MSP(관리 서비스 공급자)의 Microsoft 365 Lighthouse 기준을 배포하는 Microsoft 365 Lighthouse 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 62fc9afcbf10a0cd77c2fe2d2f7140b5197dd42a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191132"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>기본 Microsoft 365 Lighthouse 배포 

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse 기준을 통해 표준 관리되는 테넌트 구성을 배포하여 고객 테넌트 내의 사용자, 장치 및 데이터를 보호할 수 있습니다. Lighthouse와 함께 표준으로 제공된 6개의 기본 기준 구성이 있습니다.

- 관리자에게 MFA 필요
- 최종 사용자에 대해 MFA 필요
- 레거시 인증 차단
- 장치에서 장치 등록 Microsoft Endpoint Manager – Azure AD 가입
- 장치용 Defender 바이러스 백신 Windows 구성
- 디바이스에 대한 Windows 정책 구성

## <a name="before-you-begin"></a>시작하기 전에

사용자 및 고객 테넌트가 요구 사항에 나열된 요구 사항을 [충족하는지](m365-lighthouse-requirements.md)Microsoft 365 Lighthouse.

## <a name="learn-more-about-the-default-baseline"></a>기본 기준에 대해 자세히 알아보시다

왼쪽 **탐색 창에서** 기준을 선택하여 기준 페이지를 열 수 있습니다. 기본 기준이 기본 테넌트 그룹(모든 테넌트)에 이미 추가된 것입니다. 기본 기준 구성을 확인하려면  기준 보기를 선택하여 기본 기준 페이지를 열 수 있습니다. 구성은 배포 단계로 나열됩니다. 배포 세부 정보 및 사용자 영향을 확인하려면 배포 단계를 선택합니다.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Default baseline page.>.":::

## <a name="deploy-a-baseline-configuration"></a>기준 구성 배포  

1. 왼쪽 탐색 페이지에서 테넌트 를 선택하여 온보드 테넌트 목록을 볼 수 있습니다. 

2. 기준 구성을 배포할 테넌트를 선택합니다.

3. 배포 **계획 탭을** 선택하여 테넌트의 배포 계획에 추가된 기준의 모든 배포 단계를 볼 수 있습니다.

4. 배포 단계를 선택하여 배포 단계 페이지를 열 수 있습니다.

5. **적용을** 선택하여 선택한 배포 단계를 테넌트에 적용합니다. 배포 단계에 "이 작업을 수행하려면 수동 단계가 필요합니다."가 표시되면 배포 단계가 올바르게 적용될 수 있도록 수동 단계를 완료해야 합니다.

## <a name="related-content"></a>관련 콘텐츠

[기준을 사용하여](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 표준 테넌트 구성 배포 개요(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)