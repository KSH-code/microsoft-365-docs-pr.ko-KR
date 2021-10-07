---
title: Microsoft 준수 관리자에서 평가 템플릿 수정
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자에서 평가 템플릿을 수정하는 방법을 이해합니다.
ms.openlocfilehash: 846c3bc02105a50863afa7caca6041d9f72a5d95
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223556"
---
# <a name="modify-assessment-templates-in-microsoft-compliance-manager"></a>Microsoft 준수 관리자에서 평가 템플릿 수정

준수 관리자에서 평가를 사용할 때 만든 평가 템플릿을 수정할 수 있습니다. 이 프로세스는 서식 [](compliance-manager-templates-create.md) 파일 데이터를 사용하여 서식 있는 Excel 업로드하는 템플릿 만들기 프로세스와 비슷합니다.

그러나 기존 서식 파일 데이터에 대한 변경 내용으로 파일 형식을 지정하는 경우 주의해야 할 사항이 있습니다. **보존하려는 기존 데이터를 덮어치지 않도록 이러한 지침을 주의 깊게 검토하는 것이 좋습니다.**

이 스프레드시트의 형식에 대한 자세한 내용은 를 사용하여 서식 파일 데이터 [Excel.](compliance-manager-templates-format-excel.md)

## <a name="format-your-excel-file-to-modify-an-existing-template"></a>기존 템플릿을 Excel 파일 형식 지정

평가 **템플릿 페이지에서** 수정하려는 템플릿을 선택하면 세부 정보   페이지가 표시됩니다. 그런 다음 **으로 내보내기 를 Excel.** 모든 Excel 파일이 다운로드됩니다. 로컬 컴퓨터로 파일을 저장합니다.

이 파일을 사용하려면 아래 섹션으로 이동하여 필요한 지침을 빠르게 찾으세요.

- [기본 템플릿 특성 편집](#edit-the-main-template-attributes)
- [개선 작업 추가](#add-an-improvement-action)
- [개선 작업의 정보 편집](#edit-an-improvement-actions-information)
- [개선 작업의 이름 변경](#change-an-improvement-actions-name)
- [개선 작업 제거](#remove-an-improvement-action)
- [컨트롤 제거](#remove-a-control)

### <a name="edit-the-main-template-attributes"></a>기본 템플릿 특성 편집

템플릿 **탭에서** 제목 열, **inScopeServices** 열 및 추가한 다른 열의 아무 항목도 편집할 수 있습니다.  그러나 제품 또는 인증 열에는 아무 항목도 **편집할** **수** 없습니다.

### <a name="add-an-improvement-action"></a>개선 작업 추가

1. 작업 **탭으로** 이동하십시오. 기존 작업 아래의 첫 번째 빈 행에 있는 필수 필드에 정보를 추가합니다.
2. **ControlFamily 탭으로** 이동하십시오. 개선 동작이 매핑되는 컨트롤이 포함된 행을 찾아야 합니다. 해당 행의 **controlActionTitle** 열에 새 동작을 추가합니다.(이 필드의 여러 작업은 세미 콜론 두 개로 구분해야 합니다. 그 사이에 공백이 없음).
3. 스프레드시트를 저장합니다.

### <a name="edit-an-improvement-actions-information"></a>개선 작업의 정보 편집

제목을 제외한 모든 개선 *작업의 정보를 변경할 수 있습니다.* B 열 이후의 셀을 편집할 수 있으며 파일을 다시 서식 파일로 가져올 때 해당 서식 파일의 개선 작업에는 업데이트된 데이터가 포함되어 있습니다.

**actionTitle(A** 열)을 편집할 수 없는 경우 준수 관리자는 이를 새로운 개선 작업으로 고려하기 때문에 편집할 수 없습니다. 개선 작업의 이름을 변경하려는 경우 바로 아래 지침을 참조하세요.

### <a name="change-an-improvement-actions-name"></a>개선 작업의 이름 변경

개선 작업의 이름을 변경하려는 경우 기존 이름을 새 이름으로 바꾸는 스프레드시트에서 명시적으로 지정해야 합니다. 다음 단계를 따릅니다:

1. 스프레드시트의 **작업** 탭에서 A 열 다음에 스프레드시트에 새 열을 추가합니다.
2. 이제 B 열이 된 이 새 열에서 1 행의 **oldActionTitle에** 해당 헤더로 넣습니다.
3. A 열의 내용을 복사하여 B열에 붙여 넣습니다. 그러면 변경하려는 기존 개선 작업 제목이 B 열에 추가됩니다.
4. A **열에서 actionTitle** 에서 이전 이름을 삭제하고 개선 작업의 새 이름으로 바 대체합니다.

컨트롤에서 참조될 때 인식하려면 개선 작업과 Microsoft 작업에 대한 작업 제목을 영어로 작성해야 합니다.

### <a name="remove-an-improvement-action"></a>개선 작업 제거

템플릿에서 개선 작업을 제거하려면 해당 작업을 참조하는 모든 컨트롤에서 제거해야 합니다. 아래 단계에 따라 스프레드시트를 수정합니다.

1. **ControlFamily** 탭에서 제거할 개선 작업의 제목을 검색합니다.
2. 나타나는 셀에서 개선 작업의 제목을 삭제합니다. 개선 작업이 해당 행에 대한 유일한 작업인 경우 컨트롤을 제거하는 전체 행을 삭제합니다.
3. 작업 **탭에서** 삭제하는 개선 작업이 포함된 행을 삭제합니다.
4. 스프레드시트를 저장합니다.

스프레드시트를 템플릿으로 다시 가져오면 템플릿에서 개선 작업이 제거됩니다.

템플릿에서 개선 작업을 제거하면 준수 관리자에서 개선 작업이 완전히 제거되지는 않습니다. 이 작업은 다른 템플릿에서 계속 참조할 수 있습니다.

### <a name="remove-a-control"></a>컨트롤 제거

컨트롤을 제거하려면 아래 단계에 따라 스프레드시트를 수정한 다음 스프레드시트를 다시 가져와야 합니다.

1. **ControlFamily** 탭의 **controlName** 열에서 제거할 컨트롤을 찾습니다.
2. 해당 컨트롤의 행을 삭제합니다.
    - 삭제된 컨트롤에 다른 컨트롤에서 참조되지 않는 개선 작업이 포함되어 있는 경우 작업 탭에서 해당 개선 작업을 **제거해야** 합니다. 그렇지 않으면 유효성 검사 오류가 표시됩니다.

3. 스프레드시트를 저장합니다.

스프레드시트를 템플릿으로 다시 가져오면 컨트롤이 템플릿에서 제거됩니다.

## <a name="modify-template-info-in-compliance-manager"></a>준수 관리자에서 템플릿 정보 수정

파일 Excel 저장한 후 다음 단계를 수행합니다.

1. 평가 템플릿 페이지를 다시 열고 템플릿을 선택합니다. 템플릿의 세부 정보 페이지에서 수정 **마법사를 시작하려면** 템플릿 수정을 선택합니다.
2. 파일 **업로드** 화면에서 찾아보기를 선택하여 Excel 파일을 찾아 업로드합니다. 
3. 파일에 문제가 없는 경우 다음 화면에 업로드된 파일의 이름이 표시됩니다. **계속하려면** 다음을 선택합니다(파일을 변경해야 하는 경우 다른 업로드 **선택).**
    - 파일에 문제가 있는 경우 맨 위에 오류 메시지가 표시됩니다. 파일을 수정하고 다시 업로드해야 합니다. 스프레드시트의 서식이 잘못되었거나 특정 필드에 잘못된 정보가 있는 경우 오류가 발생합니다.

4. 검토 **및 완료 화면에** 개선 작업 및 컨트롤의 수와 템플릿의 최대 점수가 표시됩니다. 승인할 준비가 되면 다음 을 **선택합니다.**
5. 마지막 화면은 템플릿이 수정된 것입니다. **완료를** 선택하여 마법사를 종료합니다.

이제 템플릿에 적용한 변경 내용이 포함됩니다. 이 수정된 템플릿을 사용하는 평가는 이제 보류 중인 업데이트를 표시하며, 템플릿의 변경 내용을 반영하기 위해 평가에 대한 업데이트를 수락해야 합니다. 평가 업데이트에 대해 [자세히 알아보시다.](compliance-manager-assessments.md#accept-updates-to-assessments)

> [!NOTE]
> 영어가 아는 언어로 준수 관리자를 사용하는 경우 서식 파일을 내보낼 때 일부 텍스트가 영어로 Excel. 컨트롤에서 인식하려면 작업 제목(개선 작업과 해당되는 경우 Microsoft 작업 모두)이 영어로 있어야 합니다. 작업 제목을 변경하는 경우 파일을 올바르게 가져오기 위해 영어로 작성해야 합니다.
