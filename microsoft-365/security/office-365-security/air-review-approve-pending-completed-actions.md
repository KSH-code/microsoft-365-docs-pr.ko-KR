---
title: Microsoft Defender for Office 365
keywords: AIR, autoIR, Endpoint용 Microsoft Defender, 자동화, 조사, 대응, 수정, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 계획의 자동화된 조사 및 대응 기능의 수정 조치에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 4d81fe5e2baa4146136d7e55461290a31ef2462b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196624"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>관리 센터에서 재구성 작업을 검토하고 Office 365

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](defender-for-office-365.md)

전자 메일에 대한 자동화된 조사가 & 공동 작업 콘텐츠로  인해 악성 또는 의심스러운 등의 결과가 생성되면 특정 수정 작업이 만들어집니다. Microsoft Defender for Office 365 수정 작업에는 다음이 포함됩니다.

- 전자 메일 메시지 또는 클러스터 소프트 삭제
- 외부 메일 전달 끄기

이러한 수정 작업은 보안 운영 팀이 승인하지 않는 한 수행되지 않습니다. 자동화된 조사가 제시간에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 검토하고 승인하는 것이 좋습니다. 경우에 따라 제출된 작업을 다시 검토할 수 있습니다.  작업을 수행하기 전에 역할 제거를 & 검색 역할의 일부가 되기만 합니다.

## <a name="approve-or-reject-pending-actions"></a>보류 중인 작업 승인(또는 거부)
자동 조사 작업을 찾아서 수행할 수 있는 네 가지 방법이 있습니다.

- [인시던트 큐](https://security.microsoft.com/incidents)
- [알림 센터 ](https://security.microsoft.com/action-center/pending)
- 조사 자체(인시던트 또는 경고를 통해 액세스)
- [조사 및 재구성 조사 큐](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>인시던트 큐

1. Microsoft 365 Defender 포털( <https://security.microsoft.com> )을 열고 로그인합니다.
2. 탐색 창에서 인시던트 및 **& 인시던트**> 선택합니다.
3. 문제 이름을 선택하여 요약 페이지를 열 수 있습니다.
4. 증거 및 **응답 탭을** 선택합니다.
5. 목록에서 항목을 선택합니다. 왼쪽 창이 열립니다.
6. 왼쪽 창에서 작업을 승인하거나 거부합니다.

## <a name="investigation-queue"></a>조사 큐

1. Microsoft 365 Defender 포털( <https://security.microsoft.com> )을 열고 로그인합니다.
2. 경고/인시던트 페이지에서 이동합니다.
3. 조사 페이지에서 보류 중인 작업 **탭으로** 이동합니다.
4. 목록에서 항목을 선택합니다. 왼쪽 창이 열립니다.
5. 왼쪽 창에서 작업을 승인하거나 거부합니다.

## <a name="action-center"></a>알림 센터 

1. Microsoft 365 Defender 포털( <https://security.microsoft.com> )을 열고 로그인합니다.
2. 탐색 창에서 작업 센터 **를 선택합니다.**
3. 보류 **중인 탭에서** 승인을 대기 중인 작업 목록을 검토합니다.
   - 조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.
   - **승인을** 선택하여 보류 중인 작업을 초기화합니다.
   - 보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.

## <a name="investigation-and-remediation-investigations-queue"></a>조사 및 재구성 조사 큐

1. Microsoft 365 Defender 포털( <https://security.microsoft.com> )을 열고 로그인합니다.
2. 보류 중인 조사를 개방합니다.
3. 조사 페이지에서 보류 중인 작업 **탭으로** 이동합니다.
4. 목록에서 항목을 선택합니다. 왼쪽 창이 열립니다.
5. 왼쪽 창에서 작업을 승인하거나 거부합니다.

## <a name="change-or-undo-one-remediation-action"></a>한 가지 수정 작업 변경 또는 실행 취소

제출된 작업을 다시 검토하는 방법에는 두 가지가 있습니다.

- 통합된 [작업 센터를 통해](https://security.microsoft.com/action-center)
- 그러나 [Office 센터입니다.](https://security.microsoft.com/threatincidents)

## <a name="change-or-undo-through-the-unified-action-center"></a>통합된 작업 센터를 통해 변경 또는 실행 취소

1. 통합된 작업 [센터로 이동하여](https://security.microsoft.com/action-center) 로그인합니다.
2. 사용 **기록 탭에서** 변경하거나 실행 취소할 작업을 선택합니다.
3. 화면 오른쪽의 창에서 적절한 작업(받은 편지함으로 **이동,** 정크로 이동, **삭제된** 항목으로 **이동,** 소프트 삭제 또는 영구 **삭제)을 선택합니다.**

## <a name="change-or-undo-through-the-office-action-center"></a>Office 센터를 통해 변경 또는 실행 취소

1. Office [센터로 이동하여](https://security.microsoft.com/threatincidents) 로그인합니다.
2. 적절한 수정을 선택합니다.
3. 왼쪽 창에서 메일 제출 항목을 클릭하고 목록이 로드될 때까지 기다릴 수 있습니다.
4. 맨 위에 있는 동작 단추가 활성화될 때까지 기다렸다가 동작 단추를 선택하여 작업 유형을 변경합니다.
5. 그러면 적절한 작업이 생성됩니다.

## <a name="next-steps"></a>다음 단계

- [위협 탐색기 사용](threat-explorer.md)
- [관리자 /수동 작업](remediate-malicious-email-delivered-office-365.md)
- [자동화된 조사 및 응답 기능에서 가짓 긍정/부정을 보고하는 방법](air-report-false-positives-negatives.md)

## <a name="see-also"></a>참고 항목

- [자동화된 조사의 세부 정보 및 결과를 Office 365](air-view-investigation-results.md)
