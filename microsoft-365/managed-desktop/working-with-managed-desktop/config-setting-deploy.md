---
title: Microsoft Managed Desktop에서 구성 가능한 설정 배포
description: Microsoft Managed Desktop에서 구성 가능한 설정 변경 내용을 배포 하 고 추적 합니다.
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서, 배포, 단계적 배포, 구성 가능한 설정
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.openlocfilehash: d6e669ecb2e00158dd3ce6712014244fa2f081c9
ms.sourcegitcommit: b838e1dc7a98fcce1bdf7b76173f5f04f16be703
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "30175780"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>구성 가능한 설정 배포 및 추적-Microsoft Managed Desktop

설정 범주를 변경 하 고 배포를 준비 했으면 배포 상태에 대 한 배포 진행률을 배포 하 고 추적할 수 있습니다. 이 페이지에는 구성 가능한 각 설정에 대 한 요약이 표시 됩니다. 각 배포 및 해당 세부 정보를 확인 하려면 설정 범주를 열고 변경 내용을 배포 합니다. 

## <a name="deployment-statuses"></a>배포 상태 

각 배포에 대해 볼 수 있는 동상입니다.

상태  | 설명 
--- | --- 
배포 | 변경 내용이이 링으로 배포 되기를 기다리는 중입니다.
진행 중 | 변경 내용이이 링의 활성 장치에 적용 됩니다. 
전체 | 이 링의 모든 활성 장치에서 변경 내용이 완료 되었습니다. 
Failed | 링에서 활성 장치의 10%가 변경 되지 않아 배포가 중지 되었습니다.<br><br> 배포 문제를 해결 하기 위해 Microsoft Managed Desktop 작업을 사용 하 여 지원 요청이 자동으로 열립니다. 
되돌아갑니다 | 모든 배포 링에 성공적으로 배포 된 마지막 변경 내용으로 변경 내용을 되돌렸습니다.

## <a name="deploy-changes"></a>변경 내용 배포

이 지침에서는 바탕 화면 배경 그림을 표시 합니다. 배포를 단계적으로 완료 한 후 배포 상태에서 변경 내용을 배포 합니다. 

**변경 내용을 배포 하려면**

1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **배포 상태** 작업 영역에서 배포할 설정을 선택 하 고 배포할 미리 구성 된 배포를 선택 합니다.
4. 배포 **** 를 선택 하 여 배치 링 중 하나에 변경 내용을 배포 합니다.

![구성 가능한 설정 배포 상태 개요](images/deploy-cs-overview.png)

Microsoft Managed Desktop은 Test, First, Fast, 폭넓은 순서로 배포 링에 배포할 것을 권장 합니다. 

각 링에서 변경이 완료 되 면 상태가 **완료**로 변경 됩니다.

![구성 가능한 설정 배포 완료](images/config-setting-complete.png)

## <a name="revert-deployment"></a>배포 되돌리기

이 지침에서는 바탕 화면 배경 그림을 표시 합니다. 

변경 내용을 배포한 후에는 **배포 상태**를 되돌릴 수 있습니다. **진행** 중이거나 **완료**된 변경 내용을 되돌리면 현재 배포가 중지 됩니다. 이 설정은 모든 링에 배포 된 마지막 버전으로 돌아갑니다. 

**변경 내용을 되돌리려면**
1. [Microsoft Managed Desktop administration 포털](http://aka.ms/mwaasportal) 에 로그인
2. **설정**아래에서 **보안 계정 구성**을 선택 합니다.
3. **배포 상태** 작업 영역에서 되돌리려는 설정을 선택 하 고 되돌릴 미리 구성 된 배포를 선택 합니다.
4. **이 변경 내용을 되돌릴 필요성**에서 **배포 되돌리기를**선택 합니다.

![구성 가능한 설정 배포 되돌리기](images/config-setting-revert.png) 

## <a name="additional-resources"></a>추가 리소스
- [구성 가능한 설정 개요](config-setting-overview.md)
- [구성 가능한 설정 참조](config-setting-ref.md) 