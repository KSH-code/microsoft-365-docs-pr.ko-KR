---
title: Microsoft 365 그룹을 만들 때 사용할 도메인 선택
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: PowerShell을 사용 하 여 전자 메일 주소 정책을 구성 하 여 Microsoft 365 그룹을 만들 때 사용할 도메인을 선택 하는 방법을 알아봅니다.
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377440"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Microsoft 365 그룹을 만들 때 사용할 도메인 선택

일부 조직에서는 별도의 전자 메일 도메인을 사용하여 비즈니스의 여러 부분을 분류합니다. 사용자가 Microsoft 365 그룹을 만들 때 사용 해야 할 도메인을 지정할 수 있습니다.
  
조직에서 사용자가 회사의 기본 허용 도메인이 아닌 다른 도메인에서 그룹을 만들어야 하는 경우 PowerShell을 사용 하 여 EAPs (전자 메일 주소 정책)를 구성 하 여이를 허용할 수 있습니다.

PowerShell cmdlet을 실행 하기 전에 조직에 대 한 의견을 받을 수 있는 모듈을 다운로드 하 여 설치 합니다. [원격 PowerShell을 사용 하 여 Exchange Online에 연결을](https://go.microsoft.com/fwlink/p/?LinkId=785881)확인 합니다.

## <a name="example-scenarios"></a>예제 시나리오

회사의 기본 도메인을 Contoso.com 가정해 보겠습니다. 그러나 조직의 기본 허용 도메인은 service.contoso.com입니다. 즉, 그룹은 service.contoso.com (예: jimsteam@service.contoso.com)에서 만들어집니다.
  
조직에 하위 도메인도 구성 되어 있다고 가정해 보겠습니다. 이러한 도메인에서 그룹을 만들 수도 있습니다.
  
- 학생용 students.contoso.com
    
- 교직원 용 faculty.contoso.com 구성원
    
다음 두 시나리오에서는이 작업을 수행 하는 방법에 대해 설명 합니다.

> [!NOTE]
> EAPs가 여러 개 있는 경우 우선 순위에 관계 없이 평가 됩니다. 값이 1 이면 가장 높은 우선 순위를 나타냅니다. EAP가 일치 하면 더 이상 EAP가 평가 되지 않으며, 일치 하는 EAP에 따라 그룹에 스탬프 처리 되는 주소가 나와 있습니다. > 지정 된 기준과 일치 하는 EAPs가 없는 경우 조직의 기본 허용 도메인에 그룹이 프로 비전 됩니다. 허용 도메인을 추가 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 허용 도메인 관리](https://go.microsoft.com/fwlink/p/?LinkId=785428) 를 참조 하세요.
  
### <a name="scenario-1"></a>시나리오 1

다음 예에서는 groups.contoso.com 도메인에서 조직의 모든 Microsoft 365 그룹을 구축 하는 방법을 보여 줍니다.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>시나리오 2

Microsoft 365 그룹을 만드는 하위 도메인을 제어 하려는 경우를 가정해 보겠습니다. 당신은 원합니다:
  
- Students.groups.contoso.com 도메인에서 학생이 만든 그룹 ( **부서가** **학생**에 게 설정 된 사용자) 다음 명령을 사용하세요.
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Faculty.groups.contoso.com 도메인에서 교사 구성원 (부서나 **전자 메일 주소로**설정 된 **부서** )에 의해 만들어진 그룹에 대 한 faculty.contoso.com입니다. 다음 명령을 사용하세요.
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 다른 사용자가 만든 그룹은 groups.contoso.com 도메인에 만들어집니다. 다음 명령을 사용하세요.
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>전자 메일 주소 정책 변경

기존 EAP에 대 한 우선 순위 또는 전자 메일 주소 템플릿을 변경 하려면 Set-EmailAddressPolicy cmdlet을 사용 합니다.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

EAP를 변경 해도 이미 프로 비전 된 그룹에는 영향을 주지 않습니다.
  
## <a name="delete-email-address-policies"></a>전자 메일 주소 정책 삭제

EAP를 삭제 하려면 Remove-EmailAddressPolicy cmdlet을 사용 합니다.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

EAP를 변경 해도 이미 프로 비전 된 그룹에는 영향을 주지 않습니다.
  
## <a name="hybrid-requirements"></a>하이브리드 요구 사항

조직이 하이브리드 시나리오에서 구성 된 경우 [에는 온-프레미스 Exchange 하이브리드를 사용 하 여 microsoft 365 그룹 구성을](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) 확인 하 여 조직이 microsoft 365 그룹을 만드는 데 필요한 요구 사항을 충족 하는지 확인 합니다. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>전자 메일 주소 정책 그룹 사용에 대 한 추가 정보:

알아야 할 몇 가지 추가 작업은 다음과 같습니다.
  
- 그룹을 만드는 속도는 조직에서 구성 된 EAPs의 수에 따라 달라 집니다.
    
- 관리자 및 사용자는 그룹을 만들 때 도메인을 수정할 수도 있습니다.
    
- 사용자 그룹은 이미 사용 가능한 표준 쿼리 (사용자 속성)를 사용 하 여 결정 됩니다. 지원 되는 필터링 할 수 있는 속성에 대 한 [-RecipientFilter 매개 변수의 필터링 된 속성](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) 을 확인 합니다. 
    
- 그룹에 대해 EAPs를 구성 하지 않으면 그룹을 만들 때 사용할 수 있는 기본 허용 도메인을 선택 합니다.
    
- 허용 도메인을 제거 하는 경우 먼저 EAPs를 업데이트 해야 하며, 그렇지 않으면 그룹 프로 비전이 영향을 받게 됩니다.
    
- 조직에 대해 최대 100 전자 메일 주소 정책을 구성할 수 있습니다.
    
## <a name="related-articles"></a>관련 문서

[관리 센터에서 Microsoft 365 그룹 만들기](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
