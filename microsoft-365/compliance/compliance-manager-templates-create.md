---
title: Microsoft 준수 관리자에서 평가 템플릿 만들기
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
description: Microsoft 준수 관리자에서 평가용 템플릿을 만드는 방법을 이해합니다. 서식 있는 파일 형식을 사용하여 서식 있는 서식 Excel 수정합니다.
ms.openlocfilehash: 5db58b1032f5c654f1c02b81c7d1b6929a9078c7
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223555"
---
# <a name="create-an-assessment-template-in-microsoft-compliance-manager"></a>Microsoft 준수 관리자에서 평가 템플릿 만들기

준수 관리자에서 사용자 지정 평가를 위한 사용자 지정 평가를 위한 새 템플릿을 만들기 위해 특수하게 형식이 Excel 스프레드시트를 사용하여 필요한 컨트롤 데이터를 어셈블합니다. 스프레드시트를 완료한 후 준수 관리자로 가져올 것입니다.

스프레드시트 서식 지정에 대한 자세한 내용은 를 사용하여 평가 템플릿 데이터 [Excel.](compliance-manager-templates-format-excel.md)

## <a name="required-roles"></a>필수 역할

전역 관리자 또는 준수 관리자 관리 역할이 있는 사용자만 템플릿을 만들고 수정할 수 있습니다. 역할 및 사용 [권한에 대해 자세히 알아보시고 을(를) 자세히 알아보아야 합니다.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-new-template-in-compliance-manager"></a>준수 관리자에서 새 템플릿 만들기

1. 준수 **관리자의 평가 템플릿** 페이지로 이동합니다.
2. 새 **서식 파일 만들기 를 선택합니다.** 서식 파일 만들기 마법사가 열립니다.
3. 만들 서식 파일 유형을 선택하십시오. 이 경우 사용자 지정 템플릿 **만들기를 선택하고** 다음 을 **선택합니다.**
4. 파일 **업로드** 화면에서 찾아보기를  선택하여 모든 필수 템플릿 데이터가 Excel 서식 있는 파일 형식의 파일을 찾아 업로드합니다.
5. 파일에 문제가 없는 경우 업로드된 파일의 이름이 표시됩니다. **다음** 을 선택하여 계속합니다. (파일을 변경해야 하는 경우 다른 업로드 **선택합니다.**
    - 파일에 오류가 있는 경우 맨 위에 오류 메시지가 표시됩니다. 파일을 수정하고 다시 업로드해야 합니다. 스프레드시트의 서식이 잘못되었거나 특정 필드에 잘못된 정보가 있는 경우 오류가 발생합니다.
6. 검토 **및 완료 화면에** 개선 작업 및 컨트롤의 수와 템플릿의 최대 점수가 표시됩니다. 승인할 준비가 되면 템플릿 **만들기를 선택합니다.** (변경해야 하는 경우 뒤로를 **선택합니다.)**
7. 마지막 화면에서는 새 템플릿이 만들어졌다는 확인을 표시합니다. **완료를** 선택하여 마법사를 종료합니다.
8. 새 템플릿의 세부 정보 페이지에 도착하여 평가를 [만들 수 있습니다.](compliance-manager-assessments.md#create-assessments)
