---
title: Office 365, O365 전송, Office 365 스팸 문제, O365 가양성, 검색을 위한 전자 메일 전송, office 365에서 의심 스러운 전자 메일, 메일 검색, 365 피싱에 대 한 Microsoft 검색, Microsoft scan for 피싱, submit for 스팸, 제출 전자 메일, 전송 전자 메일, dodgy 전자 메일, 잘못 된 작업자 메일, 의심 스러운, 신뢰할 수 없는 메일, 보고서 피싱 전자 메일을 microsoft에 보고 하 고 microsoft에 게 microsoft에 사기 전자 메일 신고 받은 편지함의 전자 메일 office 365, 전자 메일 office 365의 바이러스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 테 넌 트에서 의심 스러운 전자 메일, 의심 스러운 메일, 스팸 및 기타 해로운 메시지, Url 및 파일을 검색을 위해 Microsoft에 제출 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033617"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, Url 및 파일을 Microsoft에 제출

Exchange Online의 사서함이 있는 Office 365 조직의 관리자 인 경우 Office 365 보안 & 준수 센터의 전송 포털을 사용 하 여 검색을 위해 전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 제출할 수 있습니다.

전자 메일을 제출 하면 메일에 포함 된 Url 및 첨부 파일을 검사 하는 것은 물론 수신 전자 메일을 허용 했을 수 있는 모든 정책에 대 한 정보를 받게 됩니다. 메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용-보낸 사람 목록 뿐 아니라 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)과 같은 테 넌 트 수준 정책이 포함 됩니다.

전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 전송 하는 다른 방법에 대해서는 다음을 참조 하세요. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. **제출** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/reportsubmission>합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요. Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다. 스팸 방지 정책을 추가, 수정 및 삭제 하려면 **조직 관리**, **보안 관리자**또는 **보안 독자** 역할 그룹의 구성원 이어야 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- 사용자가 메시지 및 파일을 Microsoft에 전송 하는 방법에 대 한 자세한 내용은 [Report 메시지 및 파일을 microsoft에](report-junk-email-messages-to-microsoft.md)참고 하십시오.

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Office 365 스캐닝을 위해 의심 스러운 콘텐츠를 Microsoft에 게 전달 하는 방법

Microsoft로 콘텐츠를 전송 하려면 제출 페이지의 왼쪽 위에 있는 **새 제출** 단추를 클릭 합니다. 전자 메일, URL 또는 파일을 전송 하는 옵션을 사용 하 여 페이지 오른쪽에 플라이 아웃이 표시 됩니다.

### <a name="submit-a-questionable-email-to-microsoft"></a>Microsoft에 의심 스러운 전자 메일 제출

![전자 메일 전송 예](../../media/submission-flyout-email.PNG)

1. 전자 메일을 제출 하려면 **전자 메일** 을 선택 하 고 전자 메일 **네트워크 메시지 ID** 를 지정 하거나 전자 메일 파일을 업로드 합니다.

2. 정책 확인을 실행 하려는 받는 사람을 지정 합니다. 정책 확인은 사용자 또는 테 넌 트 수준 정책으로 인해 전자 메일에서 검색이 사용 되지 않는지 확인 합니다.

3. 전자 메일이 차단 되었는지 여부를 지정 합니다. 전자 메일이 차단 되어야 하는 경우 스팸, 피싱 또는 맬웨어로 차단 되어야 하는지 여부를 지정 합니다. 어떤 종류의 입력이 가능한 지 모르는 경우 가장 좋은 판단을 사용 합니다.

   - 전송 시 정책으로 인해 필터가 생략 되 면 해당 정책에 대 한 정보를 볼 수 있습니다.

   - 하나 이상의 정책으로 인해 필터가 무시 되지 않으면 몇 분 안에 검색이 완료 됩니다. 상태 링크를 클릭 하 여 전송에 대 한 추가 정보를 볼 수 있습니다. 여기에는 정책 확인 및 다시 검사 결과의 결과가 포함 됩니다. 참고 Office 365 ATP 전체 필터링 스택을 통해 전자 메일을 다시 실행 하지만 메일, URL 또는 파일의 특정 특성에 따라 부분 다시 검사를 실행 하는 것은 아닙니다.

4. **제출** 단추를 클릭 합니다.

### <a name="send-a-suspect-url-to-microsoft"></a>Microsoft에 의심 스러운 URL 보내기

![전자 메일 전송 예](../../media/submission-url-flyout.png)

1. URL을 제출 하려면 플라이 아웃에서 **url** 을 선택 합니다. 프로토콜 (**https://**)을 포함 하 여 전체 URL을 입력 합니다.

   **필터**를 선택한 경우 URL이 피싱 또는 맬웨어 인지 지정 합니다.

2. **제출** 단추를 클릭 합니다.

### <a name="submit-a-suspected-file-to-microsoft"></a>Microsoft에 의심 스러운 파일 제출

![전자 메일 전송 예](../../media/submission-file-flyout.PNG)

1. 파일을 제출 하려면 플라이 아웃에서 **파일** 을 선택 하 고 검색할 파일을 업로드 합니다.

2. **제출** 단추를 클릭 합니다.
