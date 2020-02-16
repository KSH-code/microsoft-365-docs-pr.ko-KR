---
title: 참가자 위험 관리 알림 서식 파일 (미리 보기)
description: Microsoft 365의 참가자 위험 관리 공지 서식 파일에 대해 자세히 알아보기
keywords: Microsoft 365, 참가자 위험 관리, 위험 관리, 규정 준수
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 9e114f0292b4513176cff70afa25f69532e35d86
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072812"
---
# <a name="insider-risk-management-notice-templates-preview"></a>참가자 위험 관리 알림 서식 파일 (미리 보기)

참가자 위험 관리 알림 서식 파일을 사용 하면 활동에서 정책 일치 및 알림을 생성 하는 경우 직원에 게 전자 메일 메시지를 보낼 수 있습니다. 대부분의 경우 경고를 생성 하는 직원 작업은 실수로 인 한 실수 또는 실수로 인 한 의도 없이 작업을 수행 합니다. 통지는 직원 들에 게 보다 주의 하거나, 리프레셔 교육 또는 회사 정책 리소스에 대 한 링크나 정보를 제공 하기 위한 간단한 미리 알림 역할을 합니다. 알림은 내부 준수 교육 프로그램의 중요 한 일부일 수 있으며, 위험 활동이 반복 되는 직원에 대 한 문서화 된 감사 내역을 만드는 데 도움이 될 수 있습니다.

문제 해결 프로세스의 일부로 서 사용자에 게 정책 일치에 대 한 전자 메일 미리 알림 알림을 보내려면 공지 템플릿 만들기를 선택 합니다. 검토 중인 특정 경고와 연결 된 직원 전자 메일 주소로만 알림을 보낼 수 있습니다. 정책 일치에 적용할 알림 서식 파일을 선택 하는 경우에는 서식 파일에 정의 된 필드 값을 그대로 사용 하거나 필요에 따라 필드를 덮어쓸 수 있습니다.

## <a name="notice-templates-dashboard"></a>공지 템플릿 대시보드

**알림 서식 파일 대시보드에** 는 구성 된 알림 서식 파일의 목록이 표시 되며, 새 알림 서식 파일을 만들 수 있습니다. 공지 서식 파일은 마지막에 나열 된 가장 최근 알림 서식 파일을 사용 하 여 역순 날짜 순으로 나열 됩니다.

![참가자 위험 관리 알림 서식 파일 대시보드](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>알림 HTML

알림에 대해 단순한 텍스트 기반 전자 메일 메시지를 만들려면 공지 템플릿의 메시지 본문 필드에 HTML을 사용 하 여 보다 자세한 메시지를 만들 수 있습니다. 다음은 기본 HTML 기반 전자 메일 알림 서식 파일에 대 한 메시지 본문 형식을 제공 하는 예제입니다.

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> 참가자 위험 관리 알림 서식 파일의 HTML href 특성 구현은 현재 URL 참조에 큰따옴표 대신 작은따옴표를 지원 합니다.

## <a name="create-a-new-notice-template"></a>새 공지 서식 파일 만들기

새 참가자 위험 관리 알림 서식 파일을 만들려면 Microsoft 365 준수 센터의 **참가자 위험 관리** 솔루션에서 알림 마법사를 사용 합니다.

새 참가자 위험 관리 알림 서식 파일을 만들려면 다음 단계를 완료 합니다.

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.
2. **공지 템플릿 만들기** 를 선택 하 여 알림 마법사를 엽니다.
3. **새 공지 서식 파일 만들기** 페이지에서 다음 필드를 작성 합니다.
    - **서식 파일 이름**: 알림의 이름을 입력 합니다. 이 이름은 상황에 따라 알림을 보낼 때 공지 대시보드의 공지 사항 목록 및 공지 선택 목록에 표시 됩니다.
    - **전송 원본**: 알림의 보낸 사람 전자 메일 주소를 입력 합니다. 이 주소는 대/소문자 로부터 알림을 보낼 때 변경 되지 않는 한 직원에 게 전송 되는 모든 주의 사항에 있는 **보낸 사람:** 필드에 표시 됩니다.
    - **참조 및 숨은 참조** 필드: 구독에 대 한 Active Directory에서 선택한 정책 일치에 대 한 알림을 받을 사용자 또는 그룹 (선택 사항)입니다.
    - **제목**: 메시지의 제목 줄에 표시 되는 정보는 텍스트 문자를 지원 합니다.
    - **메시지 본문**: 메시지 본문에 표시 되는 정보는 텍스트 또는 HTML 값을 지원 합니다.
4. 공지 템플릿을 만들고 저장 하려면 **만들기** 를 선택 하 고 공지 서식 파일을 저장 하지 않고 닫으려면 **취소** 를 선택 합니다.

## <a name="update-a-notice-template"></a>공지 서식 파일 업데이트

기존 참가자 위험 관리 알림 서식 파일을 업데이트 하려면 다음 단계를 완료 합니다.

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.
2. 공지 사항 대시보드에서 관리 하려는 공지 템플릿을 선택 합니다.
3. 알림 세부 정보 페이지에서 **편집** 을 선택 합니다.
4. **편집** 페이지에서는 다음 필드를 편집할 수 있습니다.
    - **서식 파일 이름**: 알림의 새 이름을 입력 합니다. 이 이름은 상황에 따라 알림을 보낼 때 공지 대시보드의 공지 사항 목록 및 공지 선택 목록에 표시 됩니다.
    - **전송 원본**: 알림의 보낸 사람 전자 메일 주소를 업데이트 합니다. 이 주소는 대/소문자 로부터 알림을 보낼 때 변경 되지 않는 한 직원에 게 전송 되는 모든 주의 사항에 있는 **보낸 사람:** 필드에 표시 됩니다.
    - **참조 및 숨은 참조** 필드: 구독에 대 한 Active Directory에서 선택한 정책 일치에 대 한 알림을 받을 수 있는 선택적 사용자 또는 그룹을 업데이트 합니다.
    - **제목**: 메시지의 제목 줄에 표시 되는 업데이트 정보는 텍스트 문자를 지원 합니다.
    - **메시지 본문**: 메시지 본문에 표시 되는 업데이트 정보는 텍스트 또는 HTML 값을 지원 합니다.
5. 알림을 업데이트 및 저장 하려면 **저장** 을 선택 하 고 공지 서식 파일을 저장 하지 않고 닫으려면 **취소** 를 선택 합니다.

## <a name="delete-a-notice-template"></a>공지 서식 파일 삭제

기존 참가자 위험 관리 알림 서식 파일을 삭제 하려면 다음 단계를 완료 합니다.

1. [Microsoft 365 준수 센터](https://compliance.microsoft.com)에서 **참가자 위험 관리** 로 이동 하 고 **공지 서식 파일** 탭을 선택 합니다.
2. 알림 대시보드에서 삭제할 알림 서식 파일을 선택 합니다.
3. 도구 모음에서 **삭제** 아이콘을 선택 합니다.
4. 공지 서식 파일을 삭제 하려면 삭제 대화 상자에서 **예** 를 선택 합니다. 삭제를 취소 하려면 **취소**를 선택 합니다.
