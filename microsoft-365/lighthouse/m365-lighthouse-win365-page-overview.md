---
title: Microsoft 365 Lighthouse Windows 365(클라우드 PC) 페이지 개요
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
description: MICROSOFT 365 LIGHTHOUSE MSP(관리 서비스 공급자)의 경우 Windows 365(클라우드 PC) 페이지에 대해 자세히 알아보십시오.
ms.openlocfilehash: b71beb0315c15929b20e1afd32a96bfd811a9ea9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211722"
---
# <a name="windows-365-cloud-pcs-page-overview"></a>Windows 365(클라우드 PC) 페이지 개요  

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)
  
Windows 365는 MEM(Microsoft Endpoint Manager) 관리자가 Windows 365 라이선스가 있는 사용자를 위해 클라우드 PC를 프로비전하고 관리할 수 있는 클라우드 기반 서비스입니다. Windows 365는 장치 관리를 위한 MEM과 완전히 통합되어 있으며, Microsoft 365 Lighthouse 모든 고객 테넌트에서 클라우드 PC의 파트너 관리에 사용할 수 있습니다.

365의 Windows 자세한 내용은 [365란 Windows 참조하세요.](/windows-365/overview) 365 요구 Windows 목록은 [Requirements for Windows 365을 참조하세요.](/windows-365/requirements)

> [!IMPORTANT]
> Lighthouse에서 관리하려면 [먼저 MEM으로](https://go.microsoft.com/fwlink/p/?linkid=2150463) 이동하여 각 고객 테넌트에 대해 클라우드 PC를 프로비전해야 합니다. Lighthouse 내에서 프로비전할 수 없는 경우

고객 테넌트에 대해 클라우드 PC를 프로비전한 후 Microsoft 365 홈 페이지의 Windows 365 카드는 프로비전에 실패한 클라우드 PC 수 및 사내 네트워크 연결 실패와 같은 조치가 필요한 클라우드 PC에 대한 간단한 경고를 제공합니다. 자세한 상태를 확인하려면 Windows 365 카드의 단추를 선택하거나 왼쪽 탐색 창에서 Windows **365를** 선택하여 Windows 365 페이지를 열 수 있습니다. 이 페이지에서는 고객 테넌트에 할당된 클라우드 PC의 상태 개요를 보고, 관리하는 모든 클라우드 PC 및 해당 클라우드 PC가 할당된 테넌트의 목록을 보고, 고객 테넌트와 Azure AD(Azure Active Directory) 간의 사내 네트워크 연결 및 상태를 확인할 수 있습니다.

## <a name="overview-tab"></a>개요 탭

개요 탭에서 색이 지정한 개수 주석 표시줄에는 네트워크 연결 실패, 프로비전되지 않은, 프로비전 실패 및 곧 프로비전되지 않은 상태인 모든 고객 테넌트의 총 클라우드 PC 또는 사내 네트워크 연결 수가 표시됩니다.

주석 표시줄 아래의 목록에서 각 고객 테넌트에 대한 클라우드 PC 상태 분석 정보를 확인할 수 있습니다. 특정 상태의 클라우드 PC가 있는 테넌트를 확인하려면 개수 주석 표시줄에서 해당 상태를 선택하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 클라우드  PC 상태를 확인하도록 테넌트 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

특정 고객 테넌트에 대한 자세한 상태 정보를 확인하려면 해당 테넌트의 상태 열에서 값을 선택합니다. 값이 있는 열에 따라, 사내 네트워크 연결 또는 모든 클라우드 **PC** 탭이 열리고 추가 정보가 표시됩니다. 

개요 탭에는 다음 옵션도 포함되어 있습니다.

- **새로 고침:** 가장 최근 클라우드 PC 데이터를 검색하려면 선택합니다.
- **내보내기:** 클라우드 PC 데이터를 콤보로 구분된 값(Excel) 파일로 내보내 .csv 선택합니다.
- **검색:** 키워드를 입력하여 목록에서 특정 클라우드 PC를 빠르게 찾습니다.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="Screenshot of the Windows 365 Overview tab.":::

## <a name="all-cloud-pcs-tab"></a>모든 클라우드 PC 탭

모든 클라우드 PC 탭의 색상이 지정한 개수 주석 표시줄에는 프로비전, 프로비전되지 않은, 프로비전 실패 및 곧 프로비전되지 않은 상태인 모든 고객 테넌트의 총 클라우드 PC 수가 표시됩니다.

주석 표시줄 아래의 목록에서 모든 클라우드 PC 및 해당 프로비전 상태를 볼 수 있습니다. 다음 정보가 제공됩니다.

- **클라우드 PC 이름:** 클라우드 PC에 할당된 이름입니다.
- **테넌트:** 클라우드 PC가 프로비전된 고객 테넌트입니다.
- **장치 이름:** Intune 장치 이름 - 클라우드 PC의 고유 식별자입니다.
- **PC 유형:** 표준 SKUS에 따라 클라우드 PC의 유형입니다.
- **상태:** 클라우드 PC의 프로비전 상태입니다.
- **사용자:** 클라우드 PC가 프로비전되거나 프로비전하려고 시도한 사용자입니다.

특정 프로비전 상태의 클라우드 PC가 있는 테넌트를 확인하려면 개수 주석 표시줄에서 해당 상태를 선택하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 클라우드 PC  프로비전 상태를 확인하도록 테넌트 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

자세한 내용을 확인하려면 목록에서 클라우드 PC를 선택합니다. 클라우드 PC에서 조치를 취해야 하는 경우 테넌트 프로비저닝 정책 및 장치 세부 정보를 볼 수 있는 옵션이 Microsoft Endpoint Manager.

모든 클라우드 PC 탭에는 다음 옵션도 포함되어 있습니다.

- **새로 고침:** 가장 최근 클라우드 PC 데이터를 검색하려면 선택합니다.
- **내보내기:** 클라우드 PC 데이터를 콤보로 구분된 값(Excel) 파일로 내보내 .csv 선택합니다.
- **검색:** 키워드를 입력하여 목록에서 특정 클라우드 PC를 빠르게 찾습니다.
- **프로비전 다시 시도:** 목록에서 프로비전 실패 상태인 클라우드 PC 1~20대를 선택한 다음 이 옵션을 선택하여 해당 클라우드 PC에 대한 프로비전을 다시 시도합니다. 

클라우드 PC 상태 및 해당 상태의 의미에 대한 전체 목록은 Windows 365 설명서 라이브러리의 클라우드 [PC](/windows-365/device-management-overview#cloud-pc-overview-page) 개요 페이지를 참조하세요.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="Screenshot of the Windows 365 All Cloud PCs tab.":::

## <a name="on-premises-network-connections-tab"></a>사내 네트워크 연결 탭

On the On-premises network connections tab, the colored count-annotation bar displays the total number of on-premises network connections across all your customer tenants that have the status: Successful connections and Failed connections.

카운트 주석 표시줄 아래의 목록에서 모든 프레미스 네트워크 연결 및 해당 연결 상태를 볼 수 있습니다.

특정 프로비전 상태가 있는 연결을 확인하려면 개수 주석 표시줄에서 해당 상태를 선택하여 목록을 필터링합니다. 하나 이상의 특정 고객 테넌트에 대한 연결  상태를 확인하도록 테넌트 드롭다운 메뉴를 사용하여 목록을 필터링합니다.

목록에서 연결을 해결하거나 조치를 취해야 하는 경우 에서 연결 세부 **정보 보기를 Microsoft Endpoint Manager.**

또한 On-premises Network Connections 탭에는 다음 옵션도 포함됩니다.

- **새로 고침:** 가장 최근 연결 데이터를 검색하려면 선택합니다.
- **내보내기:** 연결 데이터를 콤보로 구분된 값(Excel) 파일로 내보내 .csv 선택합니다.
- **검색:** 키워드를 입력하여 특정 연결을 빠르게 찾습니다.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/on-prem-network-connections-tab.png" alt-text="365 Windows 네트워크 연결 탭의 스크린샷입니다.":::

## <a name="related-content"></a>관련 콘텐츠

[365 Windows란?](/windows-365/overview) (기사)\
[Windows PC에 대한 365](/windows-365/device-management-overview) 장치 관리 개요(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)