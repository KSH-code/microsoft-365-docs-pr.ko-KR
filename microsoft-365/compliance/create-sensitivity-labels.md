---
title: 민감도 레이블 생성 및 게시
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: '모든 Microsoft Information Protection 솔루션에 대한 요구 사항: 조직의 데이터를 분류하고 보호하기 위해 민감도 레이블을 생성, 구성 및 게시합니다.'
ms.openlocfilehash: efe24585981451ef91181ecc4caabb82d45d8ea4
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753164"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>민감도 레이블과 해당 정책 생성 및 구성

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

모든 Microsoft Information Protection 솔루션(때로는 MIP로 줄여서 부름)은 [민감도 레이블](sensitivity-labels.md)을 사용하여 구현됩니다. 이러한 레이블을 만들고 게시하려면, <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>로 이동합니다. 이전 포털인 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.

먼저 앱과 다른 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다. 예를 들어 사용자가 Office 앱에서 보고 적용하도록 하려는 레이블입니다. 

그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다. 이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.

## <a name="before-you-begin"></a>시작하기 전에

조직의 전역 관리자는 민감도 레이블의 모든 측면을 작성하고 관리할 수있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [민감도 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)을 참조하십시오.

## <a name="create-and-configure-sensitivity-labels"></a>민감도 레이블 생성 및 구성

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **솔루션** > **정보 보호** 를 선택합니다.
    
    이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시** 를 선택합니다.

2. **레이블** 페이지에서 **+레이블 만들기** 를 선택하여 새 민감도 레이블 마법사를 시작합니다. 

    예를 들어, Microsoft 365 규정 준수 센터에서 다음을 수행합니다.

    ![민감도 레이블 만들기.](../media/create-sensitivity-label-full.png)

    > [!NOTE]
    > 기본적으로 테넌트에는 레이블이 없으며 레이블을 만들어야 합니다. 예제 그림에 나와 있는 레이블에 [Azure Information Protection에서 마이그레이션된](/azure/information-protection/configure-policy-migrate-labels) 기본 레이블이 표시됩니다.

3. **이 레이블에 대한 범위 정의** 페이지에서 선택한 옵션은 구성할 수 있는 설정에 대한 레이블 범위와 게시될 때 표시되는 위치를 결정합니다.

    ![민감도 레이블 범위.](../media/sensitivity-labels-scopes.png)

    - **파일 및 전자 메일** 이 선택된 경우, 이 마법사에서 Office Word 및 Outlook과 같은 민감도 레이블을 지원하는 앱에 적용되는 설정을 구성할 수 있습니다. 이 옵션이 선택되지 않은 경우, 마법사는 해당 설정의 첫 번째 페이지를 표시하지만 사용자는 설정을 구성할 수 없으며 레이블은 이들 앱에서 사용자들이 선택하도록 제공되지 않습니다.

    - **그룹 및 사이트** 가 선택된 경우, 이 마법사에서 Microsoft 365 그룹 및 Teams와 SharePoint용 사이트에 적용되는 설정을 구성할 수 있습니다. 이 옵션이 선택되지 않은 경우, 마법사는 해당 설정의 첫 번째 페이지를 표시하지만 사용자는 설정을 구성할 수 없으며 레이블은 그룹 및 사이트에 대해 사용자들이 선택하도록 제공되지 않습니다.

    **Azure Purview 자산(미리 보기)** 범위에 대한 자세한 내용은 [Azure Purview에서 내용에 자동으로 레이블을 지정](/azure/purview/create-sensitivity-label)을 참조하세요.

4. 화면에 나타나는 레이블 설정 마법사 메시지를 따릅니다.

    레이블 설정에 대한 자세한 정보는 개요 정보에서 [민감도 레이블이 수행하는 작업](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하고 개별 설정 마법사의 도움말을 사용하세요.

5. 더 많은 레이블을 만들려면 이 단계를 반복합니다. 그러나 하위 레이블을 만들려면 먼저 상위 레이블을 선택하고 **추가 작업** 에 대해 **...** 을 선택한 다음 **하위 레이블 추가** 를 선택합니다.

6. 필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다. 레이블 순서를 변경하려면 **추가 작업** 에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동** 을 선택합니다. 자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.

기존 레이블을 편집하려면 해당 레이블을 선택하고 **레이블 편집** 단추를 선택합니다.

![레이블 단추를 편집하여 민감도 레이블 편집.](../media/edit-sensitivity-label-full.png)

이 단추를 선택하면 4단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다.

사용자에게 미치는 영향을 이해하지 못하는 경우 레이블을 삭제하지 마세요. 자세한 내용은 [레이블 제거 및 삭제](#removing-and-deleting-labels) 섹션을 참조하세요. 

> [!NOTE]
> 레이블 정책을 사용하여 이미 게시된 레이블을 편집하면 마법사를 완료할 때 추가 단계가 필요하지 않습니다. 예를 들어 동일한 사용자가 변경 내용을 사용할 수 있도록 새 레이블 정책에 추가하지 않아도 됩니다. 그러나 변경 사항이 모든 앱과 서비스에 복제되려면 최대 24시간이 소요됩니다.

레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다. 레이블을 게시하려면 [레이블 정책에 추가](#publish-sensitivity-labels-by-creating-a-label-policy)해야 합니다.

> [!IMPORTANT]
> 이 **레이블** 탭에서, 새 레이블 정책을 만들어야 하는 경우가 아니면 **레이블 게시** 탭 (또는 레이블을 편집할 때 **레이블 게시** 단추)을 선택하지 마세요. 다른 레이블이나 다른 정책 설정이 필요한 경우에만 여러 레이블 정책이 필요합니다. 레이블 정책을 최대한 적게 보유하는 것이 좋습니다. 조직에 대한 레이블 정책을 하나만 보유하는 것이 일반적입니다.

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a>보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정

추가 레이블 설정은 [보안 및 준수 센터 PowerShell](/powershell/exchange/scc-powershell)에서 [Set-Label](/powershell/module/exchange/set-label) cmdlet으로 사용할 수 있습니다.

예시:

- 사용자가 로컬 언어로 레이블 이름과 도구 설명을 확인하기 위한 다국적 배포에는 *LocaleSettings* 매개 변수를 사용합니다. [다음 섹션](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)에는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트를 지정하는 예제 구성이 있습니다.

- Azure Information Protection 통합 레이블 지정 클라이언트는 레이블 색상 설정 및 레이블 적용 시 사용자 지정 속성 적용을 포함하는 광범위한 [고급 설정](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) 목록을 지원합니다. 전체 목록을 보려면 이 클라이언트의 관리자 가이드에서 [레이블의 사용 가능한 고급 설정](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요.

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>다양한 언어로 민감도 레이블을 구성하는 예제 구성입니다.

다음 예제는 도구 설명에 대한 개체 틀 텍스트를 사용하 여 "Public" 이라는 레이블의 PowerShell 구성을 보여줍니다. 이 예제에서는 프랑스어, 이탈리아어, 독일어에 대한 레이블 이름 및 도구 설명 텍스트가 구성됩니다.

이 구성의 결과로 해당 표시 언어를 사용하는 Office 앱을 사용하는 사용자는 동일한 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다. 마찬가지로, 파일 탐색기에서 파일을 레이블 지정하기 위해 Azure Information Protection 통합 레이블 클라이언트를 설치한 경우 해당 언어 버전의 Windows를 사용하는 사용자는 레이블 지정을 위해 마우스 오른쪽 단추 클릭 작업을 할 때 로컬 언어로 레이블 이름과 도구 설명을 확인할 수 있습니다.

지원해야 하는 언어의 경우에는 Office [언어 식별자](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)(언어 태그라고도 함)를 사용하여 레이블 이름 및 도구 설명에 대한 고유한 번역을 지정할 수 있습니다.

PowerShell에서 명령을 실행하기 전에 먼저 [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)해야 합니다.

```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>레이블 정책을 만들어 민감도 레이블 게시

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 **솔루션** > **정보 보호** 를 선택합니다.
    
    이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시** 를 선택합니다.

2. **레이블 정책** 탭을 선택한 다음 **레이블 게시** 를 선택하여 정책 만들기 마법사를 시작합니다.

    예를 들어, Microsoft 365 규정 준수 센터에서 다음을 수행합니다.

    ![레이블 게시.](../media/publish-sensitivity-labels-full.png)

    > [!NOTE]
    > 기본적으로 테넌트에는 레이블 정책이 없으며 레이블 정책을 만들어야 합니다. 

3. 마법사에서 **민감도 레이블을 선택하여 게시** 를 선택합니다. 앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가** 를 선택합니다.

    > [!IMPORTANT]
    > 하위 레이블을 선택한 경우 해당 상위 레이블도 선택해야 합니다.

4. 선택한 레이블을 검토하고 변경하려면 **편집** 을 선택합니다. 그렇지 않으면 **다음** 을 선택합니다.

5. 화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.

    표시되는 정책 설정은 선택한 레이블의 범위와 일치 합니다. 예를 들어 **파일 및 전자 메일** 범위만을 포함하는 레이블을 선택한 경우, **기본적으로 그룹 및 사이트에 이 레이블 적용** 및 **사용자가 그룹 및 사이트에 레이블을 적용하도록 요구** 정책 설정은 표시되지 않습니다.

    정책 설정에 대한 자세한 정보는 개요 정보에서 [레이블 정책이 수행하는 작업](sensitivity-labels.md#what-label-policies-can-do)을 참조하고 개별 설정 마법사의 도움말을 사용하세요.

    **Azure Purview 자산에 (미리 보기)** 대해 구성된 레이블의 경우: 이러한 레이블에는 연결된 정책 설정이 없습니다.

6. 다양한 사용자나 위치에 대해 다양한 정책 설정이 필요한 경우에는 이 단계를 반복합니다. 예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대한 다른 기본 레이블을 원하는 경우가 해당됩니다. 또는 레이블이 다양한 범위를 갖도록 구성한 경우가 해당됩니다.

7. 사용자에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다. 레이블 정책 순서를 변경하려면 **추가 작업** 에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동** 을 선택합니다. 자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.

마법사를 완료하면 자동으로 레이블 정책이 게시됩니다. 게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다. 사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.

기존 레이블 정책을 편집하려면 해당 정책을 선택하고 **정책 편집** 단추를 선택합니다. 

![민감도 레이블 편집.](../media/edit-sensitivity-label-policy-full.png)

이 단추를 선택하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다. 마법사를 완료하면 변경 내용이 선택된 사용자 및 서비스로 자동 복제됩니다.

Windows, MacOS, iOS 및 Android에서 Office 앱에 대한 기본 제공 레이블을 사용하면 브라우저를 새로 고치면 4시간 내에, 웹에서 Word, Excel 및 PowerPoint에 대해 1시간 이내에 새 레이블이 표시됩니다. 그러나 변경 내용이 모든 앱과 서비스에 복제되려면 최대 24시간이 소요됩니다.

민감도 레이블을 지원하는 기타 앱과 서비스는 정책 업데이트를 위한 자체 업데이트 일정과 트리거를 보유하고 있어 24시간보다 더 자주 업데이트할 수 있습니다. 설명서에서 세부 정보를 확인하세요. 예를 들어 Azure Information Protection의 통합 레이블 지정 클라이언트의 경우, [Azure Information Protection 클라이언트용 자세한 비교](/azure/information-protection/rms-client/use-client#detailed-comparisons-for-the-azure-information-protection-clients) 표의 **정책 업데이트** 줄을 확인합니다.

> [!TIP]
> 경우에 따라 민감도 레이블 및 레이블 정책이 예상대로 작동하지 않도록 지연할 수 있는 타이밍 종속성을 고려해야 합니다. 예를 들어 암호화를 적용하는 레이블에 대한 [Azure Information Protection 서비스](/azure/information-protection/prepare#group-membership-caching-by-azure-information-protection)의 새 그룹 및 그룹 구성원 변경, 네트워크 복제 대기 시간 및 대역폭 제한, 그룹 구성원 캐싱 채우기가 해당됩니다.
> 
> 각각 고유한 타이밍 주기가 있는 수많은 외부 종속성이 있으므로 최근 변경 사항에 대한 레이블 및 레이블 정책 문제 해결에 시간을 보내기 전에 24시간을 기다리는 것이 좋습니다.

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a>보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정

추가 레이블 정책 설정은 [보안 및 규정 준수 센터 PowerShell](/powershell/exchange/scc-powershell)에서 [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) cmdlet으로 사용할 수 있습니다.

Azure Information Protection 통합 레이블 지정 클라이언트는 다른 레이블 솔루션의 마이그레이션, Outlook에서 전자 메일 전송을 경고하거나 정당화하거나 차단하는 팝업 메시지 등 다양한 [고급 설정](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지원합니다. 전체 목록을 보려면 이 클라이언트의 관리자 가이드에서 [레이블 정책에 사용 가능한 고급 설정](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요.

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a>민감도 레이블과 해당 정책에 PowerShell 사용

이제 [보안 및 규정 준수 센터 PowerShell](/powershell/exchange/scc-powershell)에서 레이블 지정 관리 센터에 표시되는 모든 설정을 만들고 구성할 수 있습니다. 레이블 지정 관리 센터에서 사용할 수 없는 설정에 대해 PowerShell을 사용하는 것 외에, 이제 민감도 레이블 및 민감도 레이블 정책의 만들기 및 유지 보수를 전체적으로 스크립팅할 수 있습니다.  

지원되는 매개 변수와 값에 대한 자세한 내용은 다음 문서를 참조하세요.

- [New-Label](/powershell/module/exchange/new-label)
- [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy)
- [Set-Label](/powershell/module/exchange/set-label)
- [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy)

민감도 레이블 또는 민감도 레이블 정책의 삭제를 스크립팅해야 하는 경우에는 [Remove-Label](/powershell/module/exchange/remove-label) 및 [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy)를 사용할 수 있습니다. 그러나 민감도 레이블을 삭제하기 전에 다음 섹션을 참조하세요.

## <a name="removing-and-deleting-labels"></a>레이블 제거 및 삭제

프로덕션 환경에서는 레이블 정책에서 민감도 레이블을 제거하거나 민감도 레이블을 삭제하지 않아도 됩니다. 초기 테스트 단계를 진행하는 동안에는 이 작업 중 하나를 수행해야 하는 경우가 많습니다. 이 작업 중 하나를 수행할 때 어떻게 되는지를 확인합니다.

레이블 정책에서 레이블을 제거하는 것이 삭제하는 것보다 덜 위험하며, 필요한 경우 언제든지 레이블 정책에 다시 추가할 수 있습니다.

- 레이블이 원래 지정된 사용자에게 더 이상 게시되지 않도록 레이블 정책에서 레이블을 제거하는 경우, 다음에 레이블 정책을 새로 고칠 때 사용자가 Office 앱에서 선택할 수 있는 레이블이 더 이상 표시되지 않습니다. 그러나 레이블이 문서나 전자 메일에 적용된 경우, 레이블이 해당 콘텐츠에서 제거되지 않습니다. 레이블이 적용된 모든 암호화가 유지되고 기본 보호 템플릿은 게시된 상태로 유지됩니다. 

- 제거었지만 이전에 콘텐츠에 적용한 레이블의 경우, Word, Excel 및 PowerPoint에 대한 기본 제공 레이블을 사용하는 사용자에게 상태 표시줄에 적용된 레이블 이름이 계속 표시됩니다. 마찬가지로, 제거되었지만 SharePoint 사이트에 적용된 레이블에는 **민감도** 열에 레이블 이름이 계속 표시됩니다.

비교해보면, 레이블을 삭제하는 경우:

- 레이블에서 암호화를 적용한 경우, 이전에 보호된 콘텐츠가 계속 열려 있도록 기본 보호 서식 파일을 보관합니다. 보관된 보호 서식 파일로 인해, 새 레이블을 동일한 이름으로 만들 수 없습니다. [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate)을 사용하여 보호 서식 파일을 삭제할 수 있는 경우에도, 보관된 서식 파일로 암호화된 콘텐츠를 열 필요가 없다고 확신이 들지 않으면 이 작업을 수행하지 마세요.

- 데스크톱 앱의 경우: 메타데이터의 레이블 정보는 유지되지만, 레이블 ID와 이름 매핑은 더 이상 사용할 수 없기 때문에 사용자에게 적용된 레이블 이름이 표시되지 않으므로 사용자가 해당 콘텐츠에 레이블이 지정되지 않은 것으로 가정합니다. 레이블에서 암호화를 적용하는 경우, 암호화가 유지되며 콘텐츠를 여는 경우 사용자에게 지금 보관된 보호 서식 파일의 이름과 설명이 계속 표시됩니다.

- 웹용 Office의 경우: 사용자에게 상태 표시줄이나 **민감도** 열에 레이블 이름이 표시되지 않습니다. 해당 레이블에 암호화가 적용되지 않은 경우에만 메타데이터의 레이블 정보가 유지됩니다. 레이블에서 암호화를 적용하고 [SharePoint 및 OneDrive용 민감도 레이블](sensitivity-labels-sharepoint-onedrive-files.md)을 사용하도록 설정한 경우, 메타데이터의 레이블 정보가 제거되고 암호화가 제거됩니다. 

레이블 정책에서 민감도 레이블을 제거 하거나 민감도 레이블을 삭제하는 경우, 이 변경 사항은 모든 사용자 및 서비스에 복제 하는데 최대 24시간이 걸릴 수 있습니다.

## <a name="next-steps"></a>다음 단계

특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 사용하세요.

- [민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한](encryption-sensitivity-labels.md)

- [민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)

- [팀, 그룹 및 사이트와 민감도 레이블 사용](sensitivity-labels-teams-groups-sites.md)

- [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)

레이블의 사용 방법을 모니터링하려면 [데이터 분류 시작](data-classification-overview.md)을 참조하세요.
