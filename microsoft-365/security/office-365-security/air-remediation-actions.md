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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955536"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365의 자동화 된 조사에 따라 수정 작업

## <a name="remediation-actions"></a>수정 작업

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (OFFICE 365 ATP) 계획 2의 [자동화 된 조사 및 응답 기능](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (영문)은 특정 수정 작업을 포함 합니다. 자동 조사가 실행 중이거나 완료 된 경우에는 일반적으로 보안 운영 팀의 승인이 요구 되는 하나 이상의 수정 작업을 확인할 수 있습니다. 

다음 표에서는 현재 Office 365 ATP에서 사용할 수 있는 수정 작업을 요약 하 여 보여 줍니다. 

|동작은 | 설명 |
|-----|-----|
|차단 URL(클릭 시간) |악성 Url이 포함 된 전자 메일 메시지 및 문서에 대해 보호 합니다. 이렇게 하면 사용자가 기존 Office 파일 또는 이전 전자 메일 메시지의 링크를 클릭할 때 [안전한 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 를 통해 악성 링크 및 관련 웹 페이지를 차단 하는 데 사용할 수 있습니다. |
|전자 메일 일시 삭제  |사용자 사서함에서 특정 전자 메일 메시지를 일시 삭제 합니다. <br/>일시 삭제 된 메시지는 사용자의 복구 가능한 항목 폴더로 이동 되며, 삭제 된 항목 보존 기간이 만료 될 때까지 유지 됩니다. |
|전자 메일 클러스터 일시 삭제  |모든 사용자의 사서함에서 쿼리와 일치 하는 악성 전자 메일 메시지를 일시 삭제 합니다. <br/>일시 삭제 된 메시지는 사용자의 복구 가능한 항목 폴더로 이동 되며, 삭제 된 항목 보존 기간이 만료 될 때까지 유지 됩니다. |
|외부 메일 전달 해제 |특정 최종 사용자의 사서함에서 전달 규칙을 제거 합니다.|

> [!NOTE]
> Office 365 ATP에서는 재구성 작업이 자동으로 수행 되지 않습니다. 관리 작업은 조직의 보안 팀이 승인 하는 경우에만 수행 됩니다. 

## <a name="next-steps"></a>다음 단계

- [Office 365에서 자동화 된 조사에 따라 보류 중 또는 완료 된 재구성 작업 보기](air-review-approve-pending-completed-actions.md)

- [Office 365의 자동화 된 조사에 대 한 세부 정보 및 결과](air-view-investigation-results.md)

## <a name="related-articles"></a>관련 문서

- [Microsoft Defender Advanced Threat Protection의 자동화 된 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 위협 방지](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)