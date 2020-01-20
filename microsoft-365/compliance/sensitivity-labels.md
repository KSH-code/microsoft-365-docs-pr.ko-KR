---
title: 민감도 레이블 개요
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
description: 민감도 레이블을 사용하여 사용자의 생산성 및 공동 작업 능력이 저하되지 않도록 하면서 중요한 콘텐츠를 분류 및 보호할 수 있습니다. 민감도 레이블을 사용하여 레이블이 지정된 콘텐츠에 암호화 및 워터마크를 포함하는 보호 설정을 적용할 수 있습니다.
ms.openlocfilehash: f416bcb32e9d8c14fee17d2dcecddac2aec20485
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238505"
---
# <a name="overview-of-sensitivity-labels"></a>민감도 레이블 개요

작업을 완료하기 위해 조직의 사용자는 조직 내부 및 외부의 다른 사용자와 공동으로 작업합니다. 이는 콘텐츠가 더 이상 방화벽 뒤에 있지 않으며 장치, 앱 및 서비스를 비롯한 모든 위치에서 로밍할 수 있음을 의미합니다. 또한 사용자는 로밍 중에는 조직의 비즈니스 및 준수 정책을 충족하는 안전하고 보호된 방식으로 진행하는 것이 좋습니다.

민감도 레이블을 사용하여 사용자의 생산성 및 공동 작업 능력이 저하되지 않도록 하면서 중요한 콘텐츠를 분류 및 보호할 수 있습니다.

> [!NOTE]
> 민감도 레이블은 GCC (미국 정부 커뮤니티) 조직에서 사용할 수 없습니다. 

민감도 레이블을 표시하는 예:

![Excel 리본 및 상태 표시줄의 민감도 레이블](media/Sensitivity-label-in-Excel.png)

민감도 레이블은 전역(공용) 클라우드의 테넌트에 한해서만 지원됩니다. 현재, [국가별 클라우드](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)와 같은 그 외의 클라우드의 테넌트에 대해서는 민감도 레이블이 지원되지 않습니다.

민감도 레이블을 적용하려면 사용자가 회사 또는 학교 계정으로 Office에 로그인해야 합니다.

민감도 레이블을 사용하여 다음을 수행할 수 있습니다.
  
- **레이블이 지정된 콘텐츠에 암호화 또는 워터마크와 같은 보호 설정 적용.** 예를 들어 사용자가 문서 또는 전자 메일에 기밀 레이블을 적용하면 해당 레이블이 콘텐츠를 암호화하고 기밀 워터마크를 적용할 수 있습니다.

- **다양한 플랫폼 및 장치에서 Office 앱의 콘텐츠를 보호합니다.** 지원되는 앱 목록은 [Office 앱의 민감도 레이블](sensitivity-labels-office-apps.md)을 참조하세요.

- **Windows 실행 장치에 있는 중요한 콘텐츠가 조직 외부로 유출되지 않도록 방지.** 이를 위해 Microsoft Intune의 엔드포인트 보호 기능을 사용합니다. 민감도 레이블을 Windows 장치에 상주하는 콘텐츠에 적용하면 엔드포인트 보호 기능이 콘텐츠가 Twitter 또는 Gmail과 같은 타사 앱으로 복사되거나, USB 드라이브와 같은 이동식 저장소에 복사되지 않도록 할 수 있습니다.

- Microsoft Cloud App Security를 사용하여 **타사 앱 및 서비스의 콘텐츠 보호** Cloud App Security를 사용하여 SalesForce, Box 또는 DropBox 등의 타사 앱 및 서비스에 있는 콘텐츠를 감지, 분류, 레이블 지정 및 보호할 수 있습니다. 타사 앱 또는 서비스가 민감도 레이블을 읽지 않고 지원하지 않더라도 문제가 되지 않습니다.

- **민감도 레이블을 타사 앱 및 서비스로 확장.** Microsoft Information Protection SDK를 사용할 경우 [이러한 플랫폼](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)의 타사 앱은 민감도 레이블을 읽고 보호 설정을 적용할 수 있습니다.

- **보호 설정을 사용하지 않고 콘텐츠를 분류합니다.** 사용 및 공유하는 콘텐츠와 지속 및 로밍하는 콘텐츠에 분류를 할당(예: 스티커)할 수도 있습니다. 이 분류를 사용하여 사용 현황 보고서를 생성하고 민감한 콘텐츠의 활동 데이터를 볼 수 있습니다. 이 정보를 기반으로 나중에 항상 보호 설정을 적용하도록 선택할 수 있습니다.

이러한 모든 경우에서 Office 365의 민감도 레이블은 올바른 콘텐츠에 대해 올바른 작업을 수행하는 데 도움이 될 수 있습니다. 민감도 레이블을 사용하여 사용자는 조직에서 데이터를 분류하고 해당 분류에 따라 보호 기능 설정을 적용할 수 있습니다.
  
**분류** > **민감도 레이블**에 준하여 Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 Office 365 보안 및 준수 센터에서 민감도 레이블을 만듭니다. 이러한 민감도 레이블은 Azure Information Protection, Office 앱 및 Office 365 서비스에서 사용할 수 있습니다.

Azure Information Protection 고객의 경우 다른 관리 센터에서 Azure Information Protection 레이블을 사용할 수 있으며 추가 또는 고급 구성을 수행하기로 선택한 경우 레이블이 Azure 포털과 동기화됩니다. Azure Information Protection 레이블과 Office 365 민감도 레이블은 서로 호환됩니다. 예를 들어, Azure Information Protection으로 콘텐츠의 레이블을 지정한 경우에는 콘텐츠를 다시 분류하거나 레이블을 다시 지정할 필요가 없습니다.

## <a name="what-a-sensitivity-label-is"></a>민감도 레이블이란?

문서 또는 전자 메일에 민감도 레이블을 지정하는 경우 다음과 같은 콘텐츠에 적용되는 스탬프와 같습니다.

- **사용자 지정 가능.** 조직에서다양한 수준의 중요한 콘텐츠에 대해 개인, 공개, 일반, 기밀 및 극비와 같은 범주를 만들 수 있습니다.

- **명확한 텍스트.** 레이블은 콘텐츠의 메타 데이터에 명확한 텍스트로 저장되므로 타사 앱 및 서비스는 이를 읽고 필요한 경우 고유의 보호 조치를 적용할 수 있습니다.

- **지속적.** 민감도 레이블을 컨텐츠에 적용한 후 레이블은 해당 전자 메일이나 문서의 메타 데이터에서 지속됩니다. 즉, 레이블은 보호 설정을 포함하여 콘텐트와 로밍하고 이 데이터는 정책을 적용하고 시행하는 데 기반이 됩니다.

Office 앱의 경우, 민감도 레이블이 전자 메일 또는 문서에서 사용자에게 태그와 같이 표시됩니다.

각 콘텐츠 항목에 단일 민감도 레이블을 적용할 수 있습니다. 하나의 항목에 단일 민감도 레이블과 단일 [보존 레이블](labels.md)을 모두 적용할 수 있습니다.

![민감도 레이블이 적용된 전자 메일](media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>민감도 레이블이 수행하는 작업

전자 메일 및 문서 이외에도 민감도 레이블은 여러 공개 미리 보기 릴리스에서 사용할 수 있습니다. 파일, 팀, 그룹 및 사이트에 민감도 레이블이 사용되는 방법에 관한 자세한 내용은 다음의 문서를 참조하세요.

- [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)

- [Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용](sensitivity-labels-teams-groups-sites.md)

민감도 레이블이 전자 메일이나 문서에 적용되면 해당 레이블의 구성된 보호 설정이 콘텐츠에 적용됩니다. 민감도 레이블을 사용하여 다음을 수행할 수 있습니다.

- 전자 메일만 또는 전자 메일 및 문서 모두 **암호화** 어떤 사용자 또는 그룹이 어떤 작업을 얼마나 오래 수행할 수 있는지를 선택할 수 있습니다. 예를 들어 조직 외부의 특정 도메인에 있는 사용자가 콘텐츠에 레이블이 지정된 후 7일 동안 콘텐츠를 검토할 수 있는 권한을 갖도록 선택할 수 있습니다. 또는 직접 권한을 할당하는 대신 사용자가 레이블을 적용할 때 콘텐츠에 사용 권한을 할당할 수 있습니다. 자세한 내용은 [민감도 레이블에서 암호화를 사용하여 콘텐츠 액세스 제한](encryption-sensitivity-labels.md)을 참조하세요.

- 레이블이 적용된 전자 메일 또는 문서에 사용자 지정 워터마크, 머리글 또는 바닥글을 추가하여 **콘텐츠에 표시**. 워터마크는 전자 메일이 아닌 문서에만 적용되고 255자로 제한됩니다. 또한 머리글과 바닥글은 1024자로 제한됩니다. (문서에 다른 머리글이나 바닥글 및 기타 요소가 포함되어 있는지 여부에 따라 255자로 제한되는 Excel 제외)

    ![문서에 적용된 워터마크 및 머리글](media/Sensitivity-label-watermark-header.png)

- Intune에서 끝점 보호를 설정하여 **데이터 손실 방지**. 중요한 콘텐츠를 다운로드되면 Windows 장치에서 데이터가 손실되는 것을 방지하는 데 도움이 될 수 있습니다. 예를 들어, 레이블이 지정된 콘텐츠를 Dropbox, Gmail 또는 USB 드라이브에 복사할 수 없습니다. 민감도 레이블이 WIP(Windows Information Protection)를 사용할 수 있으려면 먼저 Azure portal에서 앱 보호 정책을 만들어야 합니다. 자세한 내용은 [Windows Information Protection이 민감도 레이블로 파일을 보호하는 방법](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)을 참조하세요.

- **중요한 정보를 포함하고 있는 콘텐츠에 레이블을 자동으로 적용합니다.** 레이블을 지정할 중요한 정보의 유형을 선택할 수 있으며, 레이블을 자동으로 적용하거나 사용자가 추천 레이블을 적용할 수 있도록 메시지를 표시할 수 있습니다. 레이블을 추천하는 경우 어떤 텍스트를 선택해도 메시지가 표시됩니다. 자세한 내용은 [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md)(콘텐츠에 민감도 레이블을 자동으로 적용)를 참조하세요.

    ![필수 레이블 할당 메시지](media/Sensitivity-label-Prompt-for-required-label.png)

이러한 모든 옵션은 민감도 레이블을 만들 때 사용할 수 있습니다.

![민감도 레이블을 만들 때의 옵션](media/Sensitivity-label-create-options.png)

### <a name="label-priority-order-matters"></a>레이블 우선 순위(순서가 중요함)

관리자 센터에서 민감도 레이블을 만드는 경우 **레이블** 페이지의 **민감도** 탭에 있는 목록에 레이블이 나타납니다. 이 목록에서는 레이블의 우선 순위가 반영되기 때문에 레이블의 순서가 중요합니다. 극비와 같은 가장 제한적인 민감도 레이블은 목록의 **아래쪽**에 표시되도록 하고, 공용과 같은 가장 덜 제한적인 민감도 레이블은 **위쪽**에 표시되도록 합니다.

문서 또는 전자 메일에 하나의 민감도 레이블만 적용할 수도 있습니다. 사용자가 레이블을 더 낮은 분류로 변경하는 사유를 제공하는 옵션을 설정하는 경우 이 목록의 순서는 하위 분류를 식별합니다. 단, 이 옵션은 하위 레이블에 적용되지 않습니다.

그러나 하위 레이블의 순서는 [자동 레이블 지정](apply-sensitivity-label-automatically.md)과 함께 사용됩니다. 레이블을 자동 또는 권장 사항으로 적용되도록 구성하면 둘 이상의 레이블에 대해 여러 개의 일치 항목이 발생할 수 있습니다. 적용하거나 권장할 레이블을 결정하기 위해 레이블 순서가 사용됩니다. 마지막 민감도 레이블이 선택되고 해당하는 경우 마지막 하위 레이블이 선택됩니다.

![하위 레이블을 만들기 위한 옵션](media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>하위 레이블(레이블 그룹화)

하위 레이블을 사용하여 Office 앱에 표시되는 하나 이상의 레이블을 상위 레이블 아래에 그룹화할 수 있습니다. 예를 들어, 조직은 기밀 아래에 여러 다른 레이블을 사용하여 특정 유형의 분류를 구현할 수 있습니다. 이 예제에서 상위 레이블 ‘기밀’은 보호 설정이 지정되지 않은 단순한 텍스트 레이블이며, 하위 레이블이 있으므로 콘텐츠에 적용할 수 없습니다. 대신, 하위 레이블을 보려면 기밀을 선택해야 하며, 그 이후에 콘텐츠에 적용할 하위 레이블을 선택할 수 있습니다.

하위 레이블은 레이블을 논리 그룹으로 나타내는 간단한 방법입니다. 하위 레이블은 상위 레이블에서 설정을 상속하지 않습니다. 사용자의 하위 레이블을 게시하는 경우, 해당 사용자는 해당 하위 레이블을 콘텐츠에 적용할 수 있지만 상위 레이블만을 적용할 수는 없습니다.

상위 레이블은 Azure Information Protection 통합 레이블 지정 클라이언트를 사용하는 Office 앱에서 콘텐츠에 적용되지 않으므로 상위 레이블을 기본 레이블로 선택하거나 상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않도록 합니다.

사용자에게 하위 레이블이 표시되는 방법의 예:

![리본의 그룹화된 하위 레이블](media/Sensitivity-label-grouped-labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>민감도 레이블 편집 또는 삭제

민감도 레이블을 삭제할 경우 콘텐츠에서 레이블이 제거되지 않으며, 보호 설정이 콘텐츠에 계속 적용됩니다.

민감도 레이블을 편집하는 경우 콘텐츠에 적용된 레이블 버전이 해당 콘텐츠에 강제 적용됩니다.

## <a name="what-label-policies-can-do"></a>레이블 정책이 수행할 수 있는 작업

민감도 레이블을 만든 후 조직의 사용자들이 사용할 수 있게 게시해야 합니다. 그러면 사용자들은 해당 레이블을 콘텐츠에 적용할 수 있습니다. 모든 Exchange 사서함과 같은 위치에 게시되는 보존 레이블과 달리, 민감도 레이블은 사용자 또는 그룹에 게시됩니다. 그런 후 민감도 레이블은 해당 사용자 및 그룹을 위한 Office 앱에 나타납니다.

레이블 정책을 사용하여 다음 작업을 수행할 수 있습니다.

- **레이블을 볼 수 있는 사용자 및 그룹을 선택합니다.** 레이블을 전자 메일 사용이 가능한 보안 그룹, 메일 그룹, Office 365 그룹 또는 동적 메일 그룹에 게시할 수 있습니다.

- 레이블 정책에 포함된 사용자 및 그룹이 만든 모든 새 문서 및 전자 메일에 **기본 레이블을 적용합니다**. 이 기본 레이블은 모든 콘텐츠에 적용하려는 기본적인 보호 설정 수준을 설정할 수 있습니다.

- **레이블을 변경하는 데 사유 요구** 콘텐츠가 기밀로 표시되고 사용자가 해당 레이블을 제거하거나 더 낮은 분류(예: 공용이라는 레이블)로 바꾸려는 경우 이 작업을 수행할 때 사용자가 사유를 제공하도록 요청할 수 있습니다. 현재 사유는 관리자가 검토할 수 있도록 [레이블 분석](label-analytics.md)에 전달되지 않습니다. 그러나 [Azure Information Protection 통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)는이 정보를 [Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip)에 보냅니다.

    ![사용자가 근거를 입력하는 메시지](media/Sensitivity-label-justification-required.png)

- **사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구합니다.** 사용자의 모든 콘텐츠에 레이블을 지정하도록 하려는 경우, 사용자의 저장된 문서 및 보낸 전자 메일 모두에 레이블을 적용하도록 요구할 수 있습니다. 사용자가 레이블을 수동으로 할당하고, 레이블이 조건의 결과로 자동으로 할당되거나, 기본적으로 할당(위에 설명된 기본 레이블 옵션)될 수 있습니다. 사용자가 레이블 할당 요구를 받을 때 Outlook에 표시되는 메시지는 다음과 같습니다.

    > [!NOTE]
    > 필수 레이블에는 Azure Information Protection 구독이 필요합니다. 이 기능을 사용하려면 [Azure Information Protection 클라이언트](https://www.microsoft.com/download/details.aspx?id=53018) 또는 이후 [Azure Information Protection 통합 레이블 지정 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 중 하나를 다운로드하여 설치해야 합니다. 또한, 클라이언트는 Windows에서만 실행되므로 Mac, iOS, Android에서는 이 기능이 아직 지원되지 않습니다.

    ![사용자에게 필수 레이블을 적용하도록 요구하는 Outlook 메시지](media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)

- **사용자 지정 도움말 페이지에 도움말 링크 제공** 사용자가 민감도 레이블의 의미나 사용 방식을 잘 모를 경우 Office 앱의 **민감도 레이블** 메뉴 하단에 자세히 알아보기 URL을 제공할 수 있습니다.

    ![리본의 민감도 단추에 제공되는 자세히 알아보기 링크](media/Sensitivity-label-learn-more.png)

사용자 및 그룹에 민감도 레이블을 할당하는 레이블 정책을 만든 후에는 해당 사용자에게 Office 앱에 레이블을 확인하도록 최대 24시간을 허용할 수 있습니다.

만들고 게시할 수 있는 민감도 레이블의 수에는 제한이 없지만 한 가지 예외적인 경우가 있습니다. 레이블에 암호화가 적용되는 경우의 최대 레이블의 수는 500개입니다. 하지만 최상의 방식은 관리자 오버헤드를 낮추고 사용자의 복잡성을 줄이기 위해 레이블의 수를 최소로 유지하는 것입니다. 사용자에게 6개 이상의 주 레이블 또는 주 레이블당 6개 이상의 하위 레이블이 있는 경우 효과가 확연하게 감소하는 것이 실제 배포 결과를 통해 입증되었습니다.

### <a name="label-policy-priority-order-matters"></a>레이블 정책 우선 순위(순서 중요)

**레이블 정책** 페이지의 **민감도 정책** 탭에 있는 목록에 나타나는 민감도 레이블 정책에 민감도 레이블을 게시하여 사용자가 이를 사용할 수 있도록 합니다. 민감도 레이블([레이블 우선 순위(순서 중요)](#label-priority-order-matters) 참조)과 마찬가지로, 민감도 레이블의 순서가 우선 순위를 반영하므로 이 순서가 중요합니다. 우선 순위가 가장 낮은 레이블 정책이 **맨 위**에 표시되고 우선 순위가 가장 높은 레이블 정책이 **맨 아래**에 표시됩니다.

레이블 정책은 다음으로 구성됩니다.

- 레이블 집합.
- 정책에 포함된 사용자 및 그룹을 나타내는 레이블 정책의 범위입니다.
- 위에서 설명한 레이블 정책의 설정(기본 레이블, 맞춤, 필수 레이블 및 도움말 링크)입니다.

여러 레이블 정책에 한 사용자를 포함시키면 해당 사용자에게 해당 정책의 모든 민감도 레이블이 표시됩니다. 그러나 사용자에게는 우선 순위가 가장 높은 레이블 정책의 정책 설정만 표시됩니다.

조직의 사용자 또는 그룹이 기본 또는 필수 레이블 등 원하는 레이블 정책에서 옵션을 볼 수 없는 경우, 민감도 레이블 정책의 순서를 확인합니다. 레이블 정책의 순서를 다시 지정하려면, 민감도 레이블 정책 선택 > 오른쪽에서 줄임표 선택 > **아래로 이동** 또는 **위로 이동**합니다.

![민감도 레이블 정책에 대한 페이지에서 옵션 이동](media/sensitivity-label-policy-priority.png)

민감도 레이블 정책에 대한 우선 순위가 중요하지만, 보존 **레이블** 정책에 대해서는 중요하지 않습니다. [보존 원칙 또는 우선 순위](labels.md#the-principles-of-retention-or-what-takes-precedence)에 설명된 대로, 콘텐츠에 많은 보존 정책이 적용될 수 있습니다.

## <a name="how-to-get-started-with-sensitivity-labels"></a>민감도 레이블을 시 하는 방법

다음 절차에 따라 민감도 레이블 시작

1. **레이블을 정의합니다.** 먼저, 콘텐츠의 다양한 민감도 수준을 정의하기 위해 분류를 설정합니다. 사용자가 이해할 수 있는 일반적인 이름이나 용어를 사용합니다. 예를 들어 개인, 공용, 일반, 기밀, 고도의 기밀과 같은 레이블로 시작할 수 있습니다. 하위 레이블을 사용하여 범주별로 비슷한 레이블을 그룹화할 수 있습니다. 또한 레이블을 만들 때 사용자가 마우스로 리본의 레이블 옵션을 가리킬 때 Office 앱에 표시되는 툴팁이 필요합니다.

2. **각 레이블이 수행할 수 있는 작업을 정의합니다.** 그런 다음 각 레이블과 연결할 보호 설정을 구성합니다. 예를 들어, 민감도가 낮은 콘텐츠(“일반” 레이블 등)에는 간단히 머리글이나 바닥글을 적용하고, 민감도가 높은 콘텐츠("기밀" 레이블 등)에는 워터마크, 암호화 및 WIP를 적용하여 권한이 있는 사용자만 액세스하도록 할 수 있습니다.

3. **레이블을 받는 사용자 정의.** 조직의 레이블을 정의한 후에 해당 레이블을 보는 사용자 및 그룹을 제어하는 레이블 정책에 게시합니다. 단일 레이블을 다시 사용할 수 있습니다. 즉, 한 번 정의한 후 다른 사용자에게 할당되는 여러 레이블 정책에 포함할 수 있습니다. 그렇지만 레이블을 콘텐츠에 할당하려면 Office 앱 및 기타 서비스에서 사용할 수 있도록 해당 레이블을 먼저 게시해야 합니다. 처음 사용하는 경우 소수의 사용자에게만 할당하여 민감도 레이블을 시험해볼 수 있습니다.

다음은 관리자, 사용자 및 Office 앱이 민감도 레이블 사용을 위해 수행하는 작업의 기본 흐름입니다.

![민감도 레이블의 워크플로를 보여 주는 다이어그램](media/Sensitivity-label-flow.png)

절차 정보에 대한 정보는 [민감도 레이블과 해당 정책 생성 및 구성](create-sensitivity-labels.md)을 참조하세요.

## <a name="where-sensitivity-labels-can-appear"></a>민감도 레이블이 표시될 수 있는 위치

민감도 레이블은 Office 앱의 UI에 표시되며 리본의 홈 탭에 있는 **민감도** 단추에서 선택할 수 있습니다. 특정 앱 및 플랫폼의 기본 제공 레이블 지정에 대한 현재 가용성을 확인하려면 [앱의 민감도 레이블 기능 지원](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)을 참조하세요.

Windows 컴퓨터에 Azure Information Protection 통합 레이블 지정 클라이언트를 사용 하는 경우 민감도 레이블에 대한 추가 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 컴퓨터에 대한 레이블 지정 클라이언트 비교](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)를 참조하세요.

### <a name="office-apps-on-windows"></a>Windows의 Office 앱

Windows를 실행하는 장치의 Office 앱에서 민감도 레이블은 리본의 **홈** 탭에 있는 **민감도** 단추에 표시됩니다. 

기본 제공 레이블 지정을 사용하는 경우 적용된 레이블은 창 아래쪽에 있는 상태 표시줄에도 표시됩니다.

![Windows의 Excel 리본에 포함된 민감도 단추](media/Sensitivity-label-Sensitivity-button.png)

### <a name="office-apps-on-the-web"></a>웹용 Office 앱

웹에서 Office 앱에서의 민감도 레이블의 사용에 대한 내용은 [Office-Web 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)을 참조하세요.

### <a name="office-apps-on-mac"></a>Mac의 Office 앱

Mac 장치의 Office 앱에서 민감도 레이블은 리본의 **홈** 탭에 있는 **민감도** 단추에 표시됩니다. 적용된 레이블은 창 아래쪽에 있는 상태 표시줄에도 표시됩니다.

![Mac의 Office 리본에 포함된 민감도 단추](media/Sensitivity-label-on-Mac.png)

### <a name="office-apps-on-ios"></a>iOS의 Office 앱

iOS 장치의 Office 앱에서 민감도 레이블은 리본의 **홈** 탭에 있는 **민감도** 단추에 표시됩니다. 적용된 레이블은 창 아래쪽에 있는 상태 표시줄에도 표시됩니다.

![iOS의 Office 리본에 포함된 민감도 단추](media/Sensitivity-label-on-iOS.png)

### <a name="office-apps-on-android"></a>Android의 Office 앱

Android 장치의 Office 앱에서 민감도 레이블은 리본의 **홈** 탭에 있는 **민감도** 단추에 표시됩니다. 적용된 레이블은 창 아래쪽에 있는 상태 표시줄에도 표시됩니다.

![Android의 Office 리본에 포함된 민감도 단추](media/Sensitivity-label-on-Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a>Office 앱의 민감도 레이블에 대한 자세한 내용

- [Office 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [Office 파일에 민감도 레이블을 적용할 때의 알려진 문제](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
- [Office 앱의 민감도 레이블](sensitivity-labels-office-apps.md)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a>민감도 레이블이 기존 Azure Information Protection 레이블에 작동하는 방식

Azure Information Protection 사용자는 Azure Information Protection 통합 레이블 지정 클라이언트를 사용하여 Windows에서 콘텐츠를 분류 하고 레이블을 지정할 수 있습니다. 기존 Azure Information Protection 레이블은 통합 레이블로도 알려진 새로운 민감도 레이블과 원활하게 작동합니다. 이는 다음과 같이 사용할 수 있다는 것을 의미합니다.

- 문서 및 전자 메일의 기존 Azure Information Protection 레이블을 유지합니다.
- 기존 Azure Information Protection 레이블 구성을 유지합니다.

테넌트가 아직 [통합 레이블 지정 플랫폼](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)에 있지 않기 때문에 Azure Information Protection 레이블을 사용하는 경우, 통합 레이블 지정을 활성화할 때까지 다른 관리 센터에서 새 레이블을 만들지 않을 것을 권장합니다. 이 프로세스에 대한 자세한 내용은 [Azure Information Protection 레이블을 통합 민감도 레이블 지정으로 마이그레이션하는 방법](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)을 참조하세요.

## <a name="sensitivity-labels-and-the-azure-information-protection-client"></a>민감도 레이블 및 Azure Information Protection 클라이언트

Azure Information Protection 클라이언트가 설치된 경우 Office 365 ProPlus 앱은 Office Windows 앱에서 기본으로 제공되는 민감도 레이블 지정 기능을 자동으로 해제합니다.
이 기본 설정을 변경하여 기본으로 제공되는 레이블 지정 기능을 사용하려면 [Office 기본 제공 레이블 지정 클라이언트](sensitivity-labels-office-apps.md#about-the-office-built-in-labeling-client)를 참조하세요.

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a>Microsoft Intune에서 엔드포인트 보호 기능을 사용하여 Windows 장치에서 콘텐츠 보호

민감도 레이블을 만들 때 콘텐츠를 Windows 장치에 저장하는 경우 이 레이블이 지정된 파일을 데이터 누출로부터 보호해야 한다고 Windows에 알리는 옵션이 있습니다. 이 옵션을 사용하면 이 레이블이 지정된 콘텐츠를 엔드포인트에 저장하는 경우에도 승인된 위치로만 레이블이 공유되거나 복사되도록 확인할 수 있습니다. 본질적으로 민감도 레이블에 이 옵션을 사용하면 데이터가 추가적 사용 제약 조건을 보장받는 특별히 중요한 데이터임을 Windows에 알리게 됩니다.

이 옵션을 설정하면 Windows는 문서의 민감도 레이블을 읽고, 이해하고, 관련 작업을 수행할 수 있으며, 관리되는 Windows 장치에 연결되는 방식에 관계없이, 콘텐트에 WIP(Windows Information Protection)를 자동으로 적용할 수 있습니다. 이를 통해 암호화 적용 여부에 관계없이, 레이블이 지정된 파일을 우연한 누출로부터 보호할 수 있습니다.

예를 들어 Windows는 사용자의 컴퓨터에 있는 Word 문서에 기밀 레이블이 적용되어 있음을 이해할 수 있고 WIP는 해당 디바이스에서 비작업 위치(예: 개인 OneDrive, 개인 전자 메일 계정, 소셜 미디어 또는 USB 드라이브)로 데이터를 복사 또는 공유하지 못하도록 하는 앱 보호 정책을 적용할 수 있습니다.

사용자가 레이블이 지정된 콘텐츠를 개인 Gmail 계정에 업로드하려고 하면 이 메시지가 표시됩니다.

![레이블이 지정된 콘텐츠를 Gmail에 복사할 수 없다는 메시지](media/Sensitivity-label-WIP-Gmail.png)

또한 사용자가 레이블이 지정된 콘텐츠를 USB 드라이브에 저장하려고 하면 다음의 메시지가 표시됩니다.

![레이블이 지정된 콘텐츠를 USB 드라이브에 복사할 수 없다는 메시지](media/Sensitivity-label-WIP-USB-drive.png)

### <a name="important-prerequisites-for-using-wip"></a>WIP 사용을 위한 중요한 필수 구성 요소

민감도 레이블이 WIP를 사용하려면, [Windows Information Protection이 민감도 레이블이 지정된 파일을 보호하는 방법](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)에 설명된 필수 구성 요소를 수행해야 합니다. 이 항목에서는 다음과 같은 필수 구성 요소에 대해 설명합니다.

- Windows 10, 버전 1809 이상을 실행 중인지 확인합니다.
- [Microsoft Defender ATP(Microsoft Defender Advanced Threat Protection) 설정](https://docs.microsoft.com/windows/security/threat-protection/)는 콘텐츠에서 레이블을 검색하고 해당 WIP 보호를 적용합니다. ATP는 WIP와 독립적으로 이상 보고와 같은 일부 작업을 수행합니다.
- 엔드포인트 장치에 적용되는 WIP(Windows Information Protection) 정책을 만듭니다. 다음 중 하나의 위치에서 이를 수행할 수 있습니다.

  - [Microsoft Intune용 Azure Portal을 사용하여 MDM으로 WIP(Windows Information Protection) 정책 만들기](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
  - [System Center Configuration Manager를 사용하여 WIP(Windows Information Protection) 정책 만들기 및 배포](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a>Microsoft Cloud App Security를 사용하여 타사 앱 및 서비스의 콘텐츠 보호

CAS(Cloud App Security)를 사용하여 타사 앱 및 서비스의 콘텐츠 보호 CAS를 사용하여 SalesForce, Box 또는 Dropbox 등의 타사 서비스 및 앱에 있는 콘텐츠를 감지, 분류, 레이블 지정 및 보호할 수 있습니다. 예를 들어, Dropbox가 민감도 레이블을 이해하지 못할 수 있으나 CAS는 해당 위치에서 레이블이 지정된 콘텐츠에 액세스하고 보호할 수 있습니다.

자세한 내용은 [Azure Information Protection 분류 레이블 자동 적용](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)을 참조하세요.

### <a name="important-prerequisites-for-using-cas"></a>CAS 사용을 위한 중요한 필수 구성 요소

민감도 레이블이 CAS를 사용하려면, [Azure Information Protection 분류 레이블 자동 적용](https://docs.microsoft.com/cloud-app-security/use-case-information-protection)에 설명된 필수 구성 요소를 수행해야 합니다. 이 항목에서는 다음과 같은 필수 구성 요소를 설명합니다.

- 테넌트에 대해 [Cloud App Security 및 Azure Information Protection을 사용하도록 설정](https://docs.microsoft.com/cloud-app-security/azip-integration)합니다.
- Cloud App Security에 [앱을 연결](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)합니다.

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a>Microsoft Information Protection SDK를 사용하여 타사 앱 및 서비스로 민감도 레이블 확장

민감도 레이블은 문서의 메타데이터에 일반 텍스트 형식으로 유지되므로 타사 앱 및 서비스에서 이러한 레이블이 포함된 콘텐츠의 식별 및 보호를 지원하도록 선택할 수 있습니다. 다른 앱 및 서비스의 지원도 항상 활장되고 있습니다.

[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/)를 사용하여 타사 앱 및 서비스는 민감도 레이블을 읽고 문서 보호에 적용할 수 있습니다. SDK는 [이러한 플랫폼](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)의 앱을 지원합니다.

이 SDK를 사용하여 Office 앱, Office 365 서비스, Azure Information Protection 검사 기능, Microsoft Cloud App Security 및 일부 기타 파트너 솔루션 등의 다른 Microsoft Information Protection 앱 및 서비스를 사용하는 방식으로 콘텐츠에 레이블을 지정하고 콘텐츠를 보호할 수 있습니다. 예를 들어, [Adobe Acrobat의 민감도 레이블 지원](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)에 대해 알아보세요.

Microsoft Information Protection SDK에 대한 자세한 내용은 [기술 커뮤니티 블로그의 발표](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)를 참조하세요. [Microsoft Information Protection과 통합된 파트너 솔루션](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)에 대해서도 알아볼 수 있습니다.

## <a name="permissions-required-to-create-sensitivity-labels"></a>민감도 레이블을 만드는 데 필요한 사용 권한

민감도 레이블을 생성할 규정 준수 팀의 구성원은 Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 Office 365 보안 및 규정 준수 센터에 대한 사용 권한이 필요합니다. 기본적으로 테넌트 관리자는 이러한 관리 센터에 액세스할 수 있으며, 규정 준수 관리자와 기타 사용자에게 테넌트 관리자의 모든 사용 권한을 부여하지 않고도 액세스를 가능하게 할 수 있습니다. 이러한 위임된 제한적 관리 액세스를 부여하려면 이들 관리 센터 중 하나의 **사용 권한** 페이지로 이동한 다음 **규정 준수 관리자** 또는 **보안 관리자** 역할 그룹에 구성원을 추가합니다.

자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)를 참조하세요.

이러한 정책은 레이블 및 레이블 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.