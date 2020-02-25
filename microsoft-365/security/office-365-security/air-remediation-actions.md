---
title: Office 365의 재구성 작업 자동화 조사 및 응답
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능의 수정 작업에 대해 알아봅니다.
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261055"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365의 자동화 된 조사에 따라 수정 작업

## <a name="remediation-actions"></a>수정 작업

Office 365의 [자동화 된 조사 및 응답 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Advanced Threat Protection은 특정 수정 작업을 포함 합니다. 자동 조사가 실행 중이거나 완료 된 경우에는 일반적으로 보안 운영 팀의 승인이 요구 되는 하나 이상의 수정 작업을 확인할 수 있습니다. 다음 표에서는 현재 Office 365 Advanced Threat Protection에서 사용할 수 있는 수정 작업을 요약 하 여 보여 줍니다. 

|동작은 | 설명 |
|-----|-----|
|차단 URL(클릭 시간) |악성 Url이 포함 된 전자 메일 및 문서에 대해 보호 합니다. 이렇게 하면 사용자가 기존 Office 파일 또는 이전 전자 메일 메시지의 링크를 클릭할 때 [안전한 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 를 통해 악성 링크 및 관련 웹 페이지를 차단 하는 데 사용할 수 있습니다. |
|전자 메일 일시 삭제  |사용자 사서함에서 특정 전자 메일 메시지 일시 삭제|
|전자 메일 클러스터 일시 삭제  |모든 사용자의 사서함에서 쿼리와 일치 하는 악성 전자 메일 메시지를 소프트 삭제|
|외부 메일 전달 해제 |특정 최종 사용자의 사서함에서 전달 규칙을 제거 합니다.|

## <a name="approve-or-reject-pending-actions"></a>보류 중인 작업 승인 (또는 거부)

![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

[조사 세부 정보](air-view-investigation-results.md)를 볼 때 보류 중인 모든 수정 작업을 승인 하거나 거부할 수 있습니다. 자동 조사가 완료 되도록 가능한 한 빨리이 작업을 수행 하는 것이 좋습니다.

> [!IMPORTANT]
> 재구성 작업을 승인 하거나 거부 하려면 적절 한 사용 권한이 필요 합니다. [AIR 기능을 사용 하려면 필수 권한을](office-365-air.md#required-permissions-to-use-air-capabilities)참조 하세요.

1. **작업** 탭을 선택 합니다.

2. 목록에서 항목을 선택 합니다. 승인 및 거부 단추가 활성화 됩니다.

3. 선택한 항목에 대해 사용 가능한 정보를 검토 하 고 작업을 승인 하거나 거부 합니다. 
 - **승인** 을 사용 하 여 업데이트를 시작할 수 있습니다.
 - **거부** 는 추가 작업을 수행 하지 않습니다.

## <a name="next-steps"></a>다음 단계

- [손상 된 사용자 보안 playbook에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [ATP 보고서 보기](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)