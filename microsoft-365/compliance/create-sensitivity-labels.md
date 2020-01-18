---
title: 민감도 레이블 생성 및 게시
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 조직의 문서 및 전자 메일을 분류하고 보호하는 데 필요한 민감도 레이블을 생성, 구성 및 게시하기 위한 지침입니다.
ms.openlocfilehash: 200b101b0083abbba90eaced9720db854ff02bbb
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233866"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>민감도 레이블과 해당 정책 생성 및 구성

[우편물 레이블을 만들고 게시하려면](sensitivity-labels.md), [Microsoft 365 준수 센터](https://compliance.microsoft.com/)와 같은 레이블 관리 센터로 이동합니다. Microsoft 365 보안 센터나 Office 365 보안 및 준수 센터를 사용할 수도 있습니다.

먼저 Office 앱과 서비스에서 사용할 수 있게 하고자 하는 민감도 레이블을 만들고 구성합니다. 그런 다음 구성한 레이블과 정책 설정을 포함하는 레이블 정책을 하나 이상 만듭니다. 이 정책은 선택된 사용자와 위치에 대한 레이블과 설정을 게시하는 레이블 정책입니다.

## <a name="create-and-configure-sensitivity-labels"></a>민감도 레이블 생성 및 구성

1. 레이블 관리 센터에서**분류** > **민감도 레이블**로 이동합니다.

2. **레이블** 탭에서 **+레이블 만들기**를 선택하 여 **새 민감도 레이블** 마법사를 시작합니다.

3. 레이블 설정에 대한 지시를 따릅니다.
    
    레이블 설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 민감도 레이블](sensitivity-labels.md#what-sensitivity-labels-can-do)을 참조하세요.

4. 이 단계를 반복하여 레이블을 더 만듭니다. 그러나 하위 레이블을 만들고자 하는 경우 먼저 상위 레이블을 선택하고 **추가 작업**에서 **...** 을 선택한 다음 **하위 레이블 추가**를 선택합니다.

5. 필요한 레이블을 모두 만든 경우 해당 주문을 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다. 레이블 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다. 자세한 내용은 개요 정보에서 [레이블 우선 순위(순서가 중요함)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.

기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택합니다. 이렇게 하면 3단계에서 모든 레이블 설정을 변경할 수 있는 **민감도 레이블 편집** 마법사가 시작됩니다. 레이블 정책을 사용하여 레이블을 이미 게시한 경우에는 추가 단계가 필요 하지 않지만 변경 사항이 사용자 및 위치로 복제될 때까지 최대 24시간이 소요됩니다.

레이블을 게시할 때까지 레이블을 앱이나 서비스에서 선택할 수 없습니다. 레이블을 게시하려면 레이블 정책에 추가해야 합니다.

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 설정

추가 레이블 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.

예를 들어 *LocaleSettings* 매개 변수를 사용하여 레이블 이름 및 도구 설명에 다른 언어를 지정할 수 있습니다. 

이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수도 있습니다. 이 고급 설정에는 레이블 색상 설정이 포함되며, 레이블이 적용된 경우에는 사용자 지정 속성 적용이 포함됩니다. 전체 목록을 확인하려면 [레이블 정책에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)을 참조하세요. 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>레이블 정책을 만들어 민감도 레이블 게시

1. 레이블 관리 센터에서 **분류** > **민감도 레이블**로 이동합니다.

2. **레이블 정책** 탭을 선택합니다.

3. **레이블 게시**를 선택하여 **정책 만들기 마법사**를 시작합니다.

4. **민감도 레이블을 선택하여 게시**를 선택합니다. 앱과 서비스에서 사용할 수 있도록 설정할 레이블을 선택한 다음 **추가**를 선택합니다.

5. 선택한 레이블을 검토하 고 내용을 변경하려면 **편집**을 선택합니다. 그렇지 않으면 **다음**을 선택합니다.

6. 화면에 나타나는 메시지에 따라 정책 설정을 구성합니다.
    
    설정에 대한 자세한 정보는 개요 정보에서 [할 수 있는 레이블 정책](sensitivity-labels.md#what-label-policies-can-do)을 참조하세요.

7. 여러 사용자나 위치에 대해 서로 다른 정책 설정이 필요한 경우에는 이 단계를 반복합니다. 예를 들어 사용자 그룹에 대한 추가 레이블이나 사용자 하위 집합에 대해 다른 기본 레이블을 원하는 경우가 해당됩니다.

8. 사용자 또는 위치에 충돌이 발생할 수 있는 레이블 정책을 여러 개 만드는 경우에는 정책 순서를 검토하고 필요한 경우 해당 항목을 위나 아래로 이동합니다. 레이블 정책 순서를 변경하려면 **추가 작업**에 대해 **...** 를 선택한 다음 **위로 이동** 또는 **아래로 이동**을 선택합니다. 자세한 내용은 개요 정보에서 [레이블 정책 우선 순위(순서가 중요함)](sensitivity-labels.md#label-policy-priority-order-matters)를 참조하세요.

마법사를 완료하면 자동으로 레이블 정책이 게시됩니다. 게시된 정책을 변경하려면 정책을 편집하기만 하면 됩니다. 사용자가 선택할 특정 게시 또는 재게시 작업이 없습니다.

기존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택합니다. 이렇게 하면 포함할 레이블과 레이블 설정을 편집할 수 있는 **정책 만들기** 마법사가 시작됩니다. 마법사를 완료하면 변경 내용이 선택된 사용자 및 위치로 자동 복제됩니다. 복제를 완료하기 위해 최대 24시간을 허용하세요.

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Office 365 보안 및 준수 센터 PowerShell를 이용한 추가 레이블 정책 설정

추가 레이블 정책 설정은 [Office 365 보안 및 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)에서 [레이블 설정](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet을 통해 사용할 수 있습니다.

이 cmdlet을 사용하여 Azure Information Protection 통합 레이블 클라이언트에 대한 [고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)을 지정할 수 있습니다. 이 고급 설정에는 Outlook에 다른 기본 레이블 설정이 포함되어 있으며, Outlook에서 보내는 전자 메일에 대해 경고, 정렬 또는 차단하는 팝업 메시지를 구현합니다. 전체 목록을 확인하려면 [레이블에 대해 사용 가능한 고급 설정](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)을 참조하세요. 

이 cmdlet을 사용하여 레이블 정책에서 레이블을 추가하거나 제거할 수도 있습니다.


## <a name="next-steps"></a>다음 단계

특정 시나리오에 대해 민감도 레이블을 구성하고 사용하려면 다음 문서를 참조하세요.

- [민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한](encryption-sensitivity-labels.md)

- [민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)

- [팀, 그룹 및 사이트와 민감도 레이블 사용](sensitivity-labels-teams-groups-sites.md)

- [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)

레이블이 사용되는 방식을 모니터링 하려면 [레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)를 참조하세요.