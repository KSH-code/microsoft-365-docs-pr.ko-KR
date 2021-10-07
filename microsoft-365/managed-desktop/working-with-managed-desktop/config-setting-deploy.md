---
title: 구성 가능한 설정 배포를 Microsoft Managed Desktop
description: 구성 가능한 설정 변경 내용을 배포하고 추적할 수 Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9a541ccf5a7bcd4197e1b24a2a6667995c08ea7f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177018"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>구성 가능한 설정 배포 및 추적 - Microsoft Managed Desktop

설정 범주를 변경하고 배포를 단계별로 변경한 후 배포 상태 페이지에서는 그룹에 설정을 배포할 수 있습니다. 이 페이지에는 구성 가능한 각 설정에 대한 요약이 표시됩니다. 설정 범주를 열면 그룹에 설정을 배포하고 이러한 배포의 진행률을 추적할 수 있습니다.

## <a name="deployment-statuses"></a>배포 상태

다음은 각 배포에 대해 확인할 수 있는 상태입니다.

상태 | 설명
--- | ---
배포 | 변경이 이 그룹에 배포 대기 중입니다.
진행 중 | 이 그룹의 활성 장치에 변경이 적용됩니다.
전체 | 이 그룹의 모든 활성 장치에서 변경이 완료되었습니다.
실패 | 그룹의 활성 장치의 10%에서 변경이 실패하여 배포가 중지되었습니다.<br><br> 배포 문제를 해결하기 위한 Microsoft Managed Desktop 지원 요청이 자동으로 열립니다.
되전 | 변경된 변경은 모든 배포 그룹에 성공적으로 배포된 마지막 변경으로 되 고쳤습니다.

## <a name="deploy-changes"></a>변경 내용 배포

이 지침에서는 바탕 화면 배경 그림을 보여 준다고 합니다. 배포를 구성한 후 배포 상태 페이지에서 변경 내용을 배포합니다.

**변경 내용을 배포하는 경우**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 배포 **상태** 작업 영역에서 배포할 설정을 선택한 다음 배포할 단계적 배포를 선택합니다.
4. 배포 **그룹** 중 하나에 변경을 배포하려면 배포를 선택합니다.

> [!NOTE]
> 주황색 주의 아이콘은 배포에 사용할 수 있는 이전 그룹이 있습니다. 순서대로 배포하는 것이 좋습니다.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

테스트, 첫 번째, 빠르기, 광범위 순서대로 배포 그룹에 배포하는 것이 좋습니다. 

각 그룹에서 변경이 완료되면 상태가 완료로 **변경됩니다.**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>배포 되버리기

변경을 배포한 후 배포 상태 에서 **되전할 수 있습니다.** 진행 중 또는 완료인  변경을 되전하면 현재 배포가 중지됩니다. 이 설정은 모든 그룹에 배포된 마지막 버전으로 되버됩니다.

예를 들어 데스크톱 배경 그림을 사용하여 변경을 되전하는 단계를 보여 주겠습니다. 

**변경을 되버리기 위해**

1. 로그인하여 [](https://endpoint.microsoft.com/) Microsoft Endpoint Manager **메뉴로** 이동합니다.
2. Microsoft Managed Desktop 를 찾아 를 **설정.**
3. 배포 **상태** 작업 영역에서 되전할 설정을 선택한 다음 되전할 단계적 배포를 선택합니다.
4. 이 **변경을 되전해야 하나요?** 에서 배포 **되전을 선택합니다.**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>추가 리소스

- [구성 가능한 설정 개요](config-setting-overview.md)
- [구성 가능한 설정 참조](config-setting-ref.md) 
