---
title: Microsoft 365 Lighthouse 위협 관리 페이지 개요
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
description: 서비스를 사용하는 MSP(관리 서비스 공급자)Microsoft 365 Lighthouse 위협 관리 페이지에 대해 자세히 알아보십시오.
ms.openlocfilehash: f9ed274b295b40f9784a193a02dad925462a6e9e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212482"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse 위협 관리 페이지 개요 

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

**적용 대상:**

- Windows 10

Microsoft Defender 바이러스 백신 바이러스, 맬웨어 및 스파이웨어를 비롯한 소프트웨어 위협으로부터 테넌트, 사용자 및 장치를 보호합니다. 이 구성은 기본 제공되고 Windows 10 포함된 강력하고 지속적인 Microsoft 365 Business Premium.  
  
위협 관리 페이지의 Microsoft 365 Lighthouse 왼쪽 탐색 창에서 위협 관리를 선택하여 위협에 대한 고객 테넌트의 보안태세를 볼 수 있습니다.  위험을 줄이는 데 도움이 되는 주의가 필요한 테넌트, 사용자 및 장치를 볼 수 있습니다.  
  
## <a name="overview-tab"></a>개요 탭  
  
위협 관리 페이지의 개요 탭에서 모든 테넌트에서 바이러스 백신 상태를 모니터링하여 주의가 필요한 영역을 식별할 수 있습니다.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Screenshot of the Overview tab.>.":::

## <a name="threats-tab"></a>위협 탭

위협 관리 페이지의 위협 탭에서 모든 테넌트에서 활성, 완화, 해결 및 허용된 위협을 볼 수 있습니다. 또한 각 위협을 필터링하고 드릴다운하여 영향을 받는 장치, 사용자 또는 테넌트에 대해 자세히 알아보는 등 모든 테넌트에서 동시에 여러 위협을 수정할 수 있습니다.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Default baseline page.>.":::
  
다음을 통해 위협을 필터링할 수 있습니다.

- 위협 상태
- 위협 심각도
- 위협 유형
- 날짜 범위

다음 표에는 다양한 위협 상태 및 해당 정의가 나열됩니다.<br><br>

| 위협 상태 | 정의 |
|--|--|
| 활성 | 장치에서 위협이 활성화됩니다. |
| 상태 없음 | 위협 상태를 사용할 수 없습니다. 장치에서 전체 스캔을 실행하여 위협을 Microsoft Defender 바이러스 백신 합니다. |
| 작업이 실패했습니다. | 장치가 위험하지 않습니다. 작업이 실패했지만 잠재적 위협이 중지되고 디바이스에서 활성화되지 않습니다. 장치에서 전체 스캔을 실행합니다. |
| 필요한 수동 단계 | 위협이 중지 했지만 전체 검사 또는 장치 재부팅과 같은 수동 단계를 완료해야 합니다. |
| 전체 검사 필요 | 장치에 대한 전체 검사가 필요합니다. |
| 재부팅 필요 | 장치를 다시 재부팅해야 합니다. |
| 중요하지 않은 오류로 수정 | 위협이 수정되고 추가 작업이 필요하지 않습니다. |
| Quarantined | 위협이 분리된 경우 추가 작업이 필요하지 않습니다. |
| 제거됨 | 위협이 장치에서 제거되었습니다. 추가 작업이 필요하지 않습니다. |
| 정리 | Microsoft Defender 바이러스 백신 파일을 복구하고 삭제했습니다. 추가 작업이 필요하지 않습니다. |
| 허용됨 | 관리자는 위협을 장치에 유지하도록 허용됩니다. | 

## <a name="antivirus-protection-tab"></a>바이러스 백신 보호 탭

위협 관리 페이지의 바이러스 백신 보호 탭에는 모든 테넌트의 장치 및 해당 테넌트의 Microsoft Defender 바이러스 백신 표시됩니다. 상태를 평가하고 취약할 수 있는 하나 이상의 장치에 대해 조치를 취할 수 있습니다. 장치 개요, 현재 위협 및 장치 작업 상태와 같은 추가 정보를 볼 장치를 선택할 수 있습니다.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="바이러스 백신 탭의 스크린샷.":::

## <a name="related-content"></a>관련 콘텐츠

[기본 Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) 배포(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)
