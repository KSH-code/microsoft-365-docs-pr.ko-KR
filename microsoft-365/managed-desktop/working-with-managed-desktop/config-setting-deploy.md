---
title: Microsoft Managed Desktop에서 구성 가능한 설정 배포
description: Microsoft Managed Desktop에서 구성 가능한 설정 변경 내용을 배포 하 고 추적 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962245"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>구성 가능한 설정 배포 및 추적-Microsoft Managed Desktop

설정 범주를 변경 하 고 배포를 준비 했으면 배포 상태 페이지에서 그룹에 대 한 설정을 배포할 수 있습니다. 이 페이지에는 구성 가능한 각 설정에 대 한 요약이 표시 됩니다. 설정 범주를 열면 설정을 그룹에 배포 하 고 해당 배포의 진행 상태를 추적할 수 있습니다.

## <a name="deployment-statuses"></a>배포 상태 

각 배포에 대해 표시 되는 상태는 다음과 같습니다.

상태  | 설명 
--- | --- 
배포 | 변경 내용이이 그룹에 배포 되기를 기다리는 중입니다.
진행 중 | 변경 내용이이 그룹의 활성 장치에 적용 됩니다. 
작업이 | 이 그룹의 모든 활성 장치에서 변경 내용이 완료 되었습니다. 
Failed | 그룹의 활성 장치 중 10%에서 변경이 실패 하 여 배포가 중지 되었습니다.<br><br> 배포 문제를 해결 하기 위해 Microsoft Managed Desktop 작업을 사용 하 여 지원 요청이 자동으로 열립니다. 
되돌아갑니다 | 변경 내용이 모든 배포 그룹에 성공적으로 배포 된 마지막 변경 내용으로 되돌아갔습니다.

## <a name="deploy-changes"></a>변경 내용 배포

이 지침에서는 바탕 화면 배경 그림을 표시 합니다. 배포를 단계적으로 완료 한 후 배포 상태 페이지에서 변경 내용을 배포 합니다. 

**변경 내용을 배포 하려면**

1. [Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **배포 상태** 작업 영역에서 배포할 설정을 선택 하 고 배포할 미리 구성 된 배포를 선택 합니다.
4. 배포 **를 선택 하** 여 배치 그룹 중 하나에 변경 내용을 배포 합니다.

![배포 상태 작업 영역입니다. 오른쪽의 신뢰할 수 있는 사이트 창입니다. 배포 그룹 섹션에는 배포 그룹, 장치 및 상태의 세 가지 열이 있습니다. 상태 열에서 "배포"가 강조 표시 됩니다.](images/1deployedit.png)
Test, First, Fast, 폭넓은 순서로 배포 그룹에 배포 하는 것이 좋습니다. 

각 그룹에서 변경 내용이 완료 되 면 상태가 **완료**로 변경 됩니다.

![업데이트, 버전, 테스트, 처음, 빠르게, 광범위 한 열이 포함 된 배포 상태 작업 영역입니다. 프록시 행이 확장 되어 4 개의 각 배포 그룹에서 "complete"로 플래그가 지정 된 날짜를 표시 합니다.](images/2completeedit.png)

## <a name="revert-deployment"></a>배포 되돌리기

변경 내용을 배포한 후에는 **배포 상태**를 되돌릴 수 있습니다. **진행** 중이거나 **완료**된 변경 내용을 되돌리면 현재 배포가 중지 됩니다. 이 설정은 모든 그룹에 배포 된 마지막 버전으로 돌아갑니다. 

예를 들어 데스크톱 배경 그림을 사용 하 여 변경 내용을 되돌리는 단계를 보여 줍니다. 

**변경 내용을 되돌리려면**
1. [Microsoft Managed Desktop administration 포털](https://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **배포 상태** 작업 영역에서 되돌리려는 설정을 선택 하 고 되돌릴 미리 구성 된 배포를 선택 합니다.
4. **이 변경 내용을 되돌릴 필요가 있습니까?** 에서 **배포 되돌리기를**선택 합니다.

![배포 상태 작업 영역입니다. 브라우저 시작 페이지를 선택 하 고, 제출 된 변경 내용과 해당 상태에 대 한 데이터를 오른쪽의 창에서 엽니다. 맨 아래에는 "배포 되돌리기"를 선택할 수 있는 "이 변경 내용을 되돌릴 필요가 없습니다." 영역이 있습니다.](images/3revert.png) 

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 개요](config-setting-overview.md)
- [구성 가능한 설정 참조](config-setting-ref.md) 
