---
title: Microsoft 준수 관리자에서 평가 템플릿 확장
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
description: Microsoft 준수 관리자에서 평가 템플릿을 확장하여 컨트롤을 추가하고 수정하는 방법을 이해합니다.
ms.openlocfilehash: a255b3787a1da66be5882f00854d5a73cfe0352e
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223548"
---
# <a name="extend-assessment-templates-in-microsoft-compliance-manager"></a>Microsoft 준수 관리자에서 평가 템플릿 확장

준수 관리자는 기존 템플릿에 자체 컨트롤 및 개선 작업을 추가하는 옵션을 제공합니다. 이 프로세스를 템플릿 확장이라고 합니다.

템플릿을 확장하려면 평가 템플릿 또는 유니버설 평가 템플릿을 확장하는지 여부에 따라 템플릿 데이터를 Microsoft 365 특별한 지침을 사용하게 됩니다.

## <a name="extend-microsoft-365-assessment-templates"></a>평가 Microsoft 365 확장

Microsoft 365 템플릿을 확장하는 경우 Microsoft에서 릴리스한 업데이트를 받을 수 있습니다. 이 업데이트는 관련 규정 또는 제품이 변경될 때 수행될 수 [있습니다(평가에](compliance-manager-assessments.md#accept-updates-to-assessments)대한 업데이트 수락 참조).

### <a name="prepare-template-data-and-create-extension"></a>서식 파일 데이터 준비 및 확장 만들기

준비하려면 스프레드시트에서 특수하게 서식 있는 서식을 Excel 서식 있는 템플릿 데이터를 가져와야 합니다. 이 Excel 파일 형식에 설명된 형식 평가 템플릿 데이터 형식에 설명된 형식을 Excel [확장에](compliance-manager-templates-format-excel.md)대한 특별한 요구 사항이 있습니다. 오류를 방지하는 데 도움이 되는 추가 지점을 참조합니다.

- 스프레드시트에는 평가에 추가할 작업 및 컨트롤만 포함되어야 합니다.
- 스프레드시트에는 수정할 평가에 이미 있는 컨트롤이나 작업이 포함될 수 없습니다.
- 서식 파일 제목에 "확장명"(예: "GDPR – [회사 이름] 확장명")을 포함하세요. 이렇게 하면 평가 서식 파일 페이지의  목록에서 Microsoft에서 제공하는 표준 서식 파일 또는 이름이 비슷한 사용자 지정 서식 파일과는 다른 것으로 쉽게 식별할 수 있습니다.

스프레드시트의 형식을 지정한 후 아래 단계를 따릅니다.

1. 평가 템플릿 **페이지로 이동하여** 새 템플릿 **만들기 를 선택합니다.** 서식 파일 만들기 마법사가 열립니다.

2. 만들 서식 파일 유형을 선택하십시오. 이 경우 Microsoft 템플릿 **확장을 선택한** 다음 **Microsoft 서식 파일 선택 을 선택합니다.**

3. 서식 파일 선택 플라이아웃 창이 화면 오른쪽에 표시될 때 모든 템플릿 목록과 활성 또는 비활성 상태의 목록이 표시됩니다. 활성화된 **템플릿** 카운터는 현재 사용 가능한 총 개수에서 사용 중인 서식 파일 수를 보여줍니다. 제한을 초과하면 메시지 표시줄에 알림이 표시됩니다.

4. 템플릿 선택 플라이아웃 창이 화면 오른쪽에 표시됩니다. **검색을** 사용하여 원하는 서식 파일을 찾기 위한 필터 적용

5. 템플릿을 찾은 후 이름 왼쪽에 있는 라디오 단추를 선택한 다음 저장을 **선택합니다.**

6. 다음 화면에 선택한 템플릿이 표시됩니다. 올바른 경우 다음 을 **선택합니다.** (올바르지 않은 경우 **다른 템플릿** 선택을 선택하여 다시 선택합니다.)

7. 파일 **업로드** 화면에서 찾아보기를  선택하여 모든 필수 템플릿 데이터가 Excel 서식 있는 파일 형식의 파일을 찾아 업로드합니다.

8. 파일에 문제가 없는 경우 다음 화면에 업로드된 파일의 이름이 표시됩니다. **계속하려면** 다음을 선택합니다(파일을 변경해야 하는 경우 다른 업로드 **선택).**

    - 파일에 문제가 있는 경우 맨 위에 오류 메시지가 표시됩니다. 파일을 수정하고 다시 업로드해야 합니다. 스프레드시트의 서식이 잘못되었거나 특정 필드에 잘못된 정보가 있는 경우 오류가 발생합니다.

9. 검토 **및 완료 화면에** 개선 작업 및 컨트롤의 수와 템플릿의 최대 점수가 표시됩니다. 승인할 준비가 되면 다음 을 **선택합니다.** (변경해야 하는 경우 다른 파일을 **업로드 선택합니다.)**

10. 마지막 화면에서는 새 템플릿이 만들어졌다는 확인을 표시합니다. **완료를** 선택하여 마법사를 종료합니다.

11. 새 템플릿의 세부 정보 페이지에 도착합니다. 여기에서 평가 만들기 를 선택하여 **평가를 만들 수 있습니다.** 지침은 [평가 빌드 및 관리를 참조하세요.](compliance-manager-assessments.md#create-assessments)

## <a name="extend-universal-assessment-templates"></a>유니버설 평가 템플릿 확장

또한 범용 버전의 템플릿을 확장하여 제품별 평가를 사용자 지정할 수도 있습니다. 유니버설 템플릿을 사용하여 평가를 만들 때 특수 확장 템플릿이 수신됩니다. 평가에 고유한 제품 및 인증 조합이 있습니다. 이 파일은 요구에 맞게 수정할 수 있습니다. 템플릿을 편집하는 방법에 대한 지침은 템플릿 [수정에 대한 지침을 참조하세요.](compliance-manager-templates-modify.md)

유니버설 서식 파일을 편집할 때 서식 파일의 모든 콘텐츠를 변경할 수 있지만 이렇게 하면 상위 서식 파일과의 상속이 중단됩니다. 즉, 상위 템플릿을 새로 고칠 경우 Microsoft에서 업데이트를 더 이상 자동으로 받지 않습니다.
