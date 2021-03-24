---
title: Microsoft Defender for Office 365에서 수정 작업 검토 및 관리
keywords: AIR, autoIR, ATP, 자동화된, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 계획 2의 자동화된 조사 및 응답 기능의 수정 작업에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073655"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Office 365에서 수정 작업 검토 및 관리

전자 메일에 대한 자동화된 조사가 & 공동 작업 콘텐츠로  인해 악성 또는 의심스러운 등의 결과가 생성되면 특정 수정 작업이 만들어집니다. Microsoft Defender for Office 365에서 수정 작업에는 다음이 포함됩니다.
- URL 차단(클릭 시간)
- 전자 메일 메시지 또는 클러스터 소프트 삭제
- 전자 메일 또는 전자 메일 첨부 파일 Quarantining
- 외부 메일 전달 끄기

이러한 수정 작업은 보안 운영 팀이 승인하지 않는 한 수행되지 않습니다. 자동화된 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인하는 것이 좋습니다. 경우에 따라 수정 작업을 실행 취소할 수 있습니다.

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a>보류 중인 작업 승인(또는 거부)

1. Microsoft 365 보안 센터()로 이동하여 <https://security.microsoft.com> 로그인합니다.
2. 탐색 창에서 작업 센터 **를 선택합니다.**
3. 보류 **중인 탭에서** 승인을 대기 중인 작업 목록을 검토합니다.
4. 목록에서 항목을 선택합니다. 플라이아웃 창이 열립니다. 
5. 플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.
   - 조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.
   - **승인을** 선택하여 보류 중인 작업을 초기화합니다.
   - 보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.

## <a name="undo-one-remediation-action"></a>한 가지 수정 작업 실행 취소

1. Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.
2. 사용 **기록 탭에서** 실행 취소할 작업을 선택합니다.
3. 화면 오른쪽 창에서 **취소를 선택합니다.**

## <a name="undo-multiple-remediation-actions"></a>여러 수정 작업 취소

1. Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.
2. 사용 **기록 탭에서** 취소할 작업을 선택합니다. 동일한 작업 유형이 있는 항목을 선택해야 합니다. 플라이아웃 창이 열립니다.
3. 플라이아웃 창에서 취소를 선택합니다.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>여러 장치에서 파일을 검지에서 제거하려면

1. Go to the Action center ( <https://security.microsoft.com/action-center> ) and sign in.
2. 사용 기록 **탭에서** 작업 유형이 **Quarantine** file인 파일을 선택합니다.
3. 화면 오른쪽 창에서 이 파일의 X **추가** 인스턴스에 적용을 선택한 다음 실행 **취소를 선택합니다.**

## <a name="next-steps"></a>다음 단계

- [위협 탐색기 사용](threat-explorer.md)
- [자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법](air-report-false-positives-negatives.md)

## <a name="see-also"></a>참고 항목

- [Office 365에서 자동화된 조사의 세부 정보 및 결과 보기](air-view-investigation-results.md)
