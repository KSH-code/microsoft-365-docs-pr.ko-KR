---
title: 안전한 첨부 파일
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: 관리자는 Microsoft Defender for Office 365의 안전 첨부 파일 기능에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2f097cddce4afe2b3242ae34bbcfa242c3af601
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206569"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 안전한 첨부 파일

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365의](defender-for-office-365.md) 안전한 첨부 파일은 [EOP(Exchange Online](anti-malware-protection.md)Protection)에서 맬웨어 방지 보호 기능으로 이미 검사된 전자 메일 첨부 파일에 대한 추가 보호 계층을 제공합니다. 특히 안전한 첨부 파일은 가상 환경을 사용하여 받는 사람에게 배달되기 전에 전자 메일 메시지의 첨부 파일을 검사합니다(확인 _프로세스)._

전자 메일 메시지에 대한 안전한 첨부 파일 보호는 안전한 첨부 파일 정책에 의해 제어됩니다. 기본 안전 첨부 파일 정책은 없습니다. 따라서 안전한 첨부 파일을 보호하려면 하나 이상의 안전 첨부 파일 정책을 **만들어야 합니다.** 자세한 내용은 [Office 365용 Defender에서 안전한](set-up-safe-attachments-policies.md)첨부 파일 정책 설정 을 참조하세요.

다음 표에서는 Office 365용 Microsoft Defender를 포함 하는 Microsoft 365 및 Office 365 조직의 안전 첨부 파일 시나리오에 대해 설명합니다(즉, 라이선스 부족은 예에서 문제가 아닙니다).

****

|시나리오|결과|
|---|---|
|Pat의 Microsoft 365 E5 조직에는 안전한 첨부 파일 정책이 구성되어 없습니다.|Pat는 안전한 첨부 파일로 보호되지 않습니다. <p> 관리자는 안전한 첨부 파일 보호 기능을 활성화하기 위해 하나 이상의 안전 첨부 파일 정책을 만들어야 합니다. 또한 Pat를 안전한 첨부 파일로 보호하려면 정책 조건에 Pat가 포함되어야 합니다.|
|이민호의 조직에는 재무 직원에게만 적용되는 안전 첨부 파일 정책이 있습니다. 이성진은 영업 부서의 구성원입니다.|이민호는 안전한 첨부 파일로 보호되지 않습니다. <p> 재무 직원은 안전한 첨부 파일로 보호되지만 영업 직원 및 기타 직원은 보호되지 않습니다.|
|어제, 홍성주 조직의 관리자는 모든 직원에게 적용되는 안전 첨부 파일 정책을 만들었다고 합니다. 오늘 이르면 이르면 님이 첨부 파일이 포함된 전자 메일 메시지를 수신했습니다.|보관은 안전한 첨부 파일로 보호됩니다. <p> 일반적으로 새 정책이 적용되는 데 30분 정도 걸립니다.|
|Chris의 조직은 조직의 모든 사용자에 대해 오랫동안 안전한 첨부 파일 정책을 제공합니다. Chris는 첨부 파일이 있는 전자 메일을 받은 다음 외부 받는 사람에게 메시지를 전달합니다.|Chis는 안전한 첨부 파일로 보호됩니다. <p> 외부 받는 사람이 조직에 안전 첨부 파일 정책이 있는 경우 전달된 메시지에는 해당 정책이 적용됩니다.|
|

안전한 첨부 파일 검색은 Microsoft 365 데이터가 있는 동일한 지역에서 진행됩니다. 데이터 센터 지리에 대한 자세한 내용은 데이터가 어디에 [있나요?를 참조하세요.](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> 다음 기능은 보안 및 준수 센터의 안전 첨부 파일 정책의 전역 & 있습니다. 그러나 이러한 설정은 전역적으로 사용 또는 사용하지 않도록 설정되어 있으며 안전 첨부 파일 정책이 필요하지 않습니다.
>
> - [SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한](mdo-for-spo-odb-and-teams.md)첨부 파일.
>
> - [Microsoft 365 E5에서 안전한 문서](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>안전 첨부 파일 정책 설정

이 섹션에서는 안전한 첨부 파일 정책의 설정에 대해 설명합니다.

- 안전한 첨부 파일 알 수 **없는 맬웨어 응답:** 이 설정은 전자 메일 메시지의 안전 첨부 파일 맬웨어 검색 작업을 제어합니다. 사용 가능한 옵션은 다음 표에 설명되어 있습니다.

  ****

  |옵션|효과|다음을 원할 때 사용:|
  |---|---|---|
  |**끄기**|첨부 파일은 안전한 첨부 파일에서 맬웨어를 검색하지 않습니다. EOP에서 맬웨어 방지 보호를 통해 메시지는 여전히 [맬웨어를 검색합니다.](anti-malware-protection.md)|선택한 받는 사람에 대한 검색을 해제합니다. <p> 내부 메일을 라우팅할 때 불필요한 지연을 방지합니다. <p> **이 옵션은 대부분의 사용자에게 권장되지 않습니다. 이 옵션을 사용하여 신뢰할 수 있는 보낸 사람의 메시지만 받는 사람에 대한 안전 첨부 파일 검색을 해제해야 합니다.**|
  |**모니터**|첨부 파일이 있는 메시지를 배달한 다음 검색된 맬웨어로 발생하는 문제를 추적합니다. <p> 안전한 첨부 파일 검사로 인해 안전한 메시지 배달이 지연될 수 있습니다.|검색된 맬웨어가 조직에서 진행되는 위치를 참조합니다.|
  |**차단**|검색된 맬웨어 첨부 파일이 있는 메시지가 배달되지 않도록 합니다. <p> 메시지는 [](manage-quarantined-messages-and-files.md) 최종 사용자가 아닌 관리자만 메시지를 검토, 해제 또는 삭제할 수 있는 경우를 위해 고지됩니다. <p> 메시지 및 첨부 파일의 향후 인스턴스를 자동으로 차단합니다. <p> 안전한 첨부 파일 검사로 인해 안전한 메시지 배달이 지연될 수 있습니다.|동일한 맬웨어 첨부 파일을 사용하여 반복되는 공격으로부터 조직을 보호합니다. <p> 이 값은 기본값으로 Standard 및 Strict 미리 설정 보안 정책의 [권장 값입니다.](preset-security-policies.md)|
  |**바꾸기**|검색된 맬웨어 첨부 파일을 제거합니다. <p> 첨부 파일이 제거되었다는 메시지를 받는 사람에게 보냅니다. <p>  메시지는 [](manage-quarantined-messages-and-files.md) 최종 사용자가 아닌 관리자만 메시지를 검토, 해제 또는 삭제할 수 있는 경우를 위해 고지됩니다. <p> 안전한 첨부 파일 검사로 인해 안전한 메시지 배달이 지연될 수 있습니다.|검색된 맬웨어로 인하여 첨부 파일이 제거된 받는 사람에게 가시성을 높입니다.|
  |**동적 배달**|메시지를 즉시 배달하지만 안전한 첨부 파일 검색이 완료될 때까지 첨부 파일을 자리 표시자로 바 대체합니다. <p> 자세한 내용은 이 문서 부분의 [안전](#dynamic-delivery-in-safe-attachments-policies) 첨부 파일 정책에서 동적 배달 섹션을 참조하십시오.|악의적인 파일로부터 받는 사람을 보호하면서 메시지 지연을 방지합니다. <p> 받는 사람이 스캔이 진행 중일 때 안전 모드에서 첨부 파일을 미리 볼 수 있습니다.|
  |

- 검색 시 첨부 파일 **리디렉션:** 리디렉션을 사용하도록 설정하고 첨부 파일을  다음 전자 메일 주소로 보내기:  **차단,** 모니터링 또는 바꾸기 작업의 경우 맬웨어 첨부 파일이 포함된 메시지를 분석 및 조사를 위해 지정된 내부 또는 외부 전자 메일 주소로 전송합니다.

  표준 및 엄격한 정책 설정에 대한 권장은 리디렉션을 사용하도록 설정하는 것입니다. 자세한 내용은 안전 첨부 파일 [설정을 참조하세요.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- **첨부 파일에** 대한 맬웨어 검색의 시간이 멀거나 오류가  발생하는 경우 위의 선택을 적용합니다. 안전한 첨부 파일 검색을 완료할 수 없는 경우에도 메시지에 대해 안전한 첨부 파일 알 수 없는 맬웨어 응답으로 지정된 작업이 수행됩니다. 리디렉션 사용 을 선택하는 경우 항상 이 **옵션을 선택합니다.** 그렇지 않으면 메시지가 손실될 수 있습니다.

- **받는 사람 필터:** 정책을 적용하는 사람을 결정하는 받는 사람 조건 및 예외를 지정해야 합니다. 조건 및 예외에 대해 다음 속성을 사용할 수 있습니다.

  - **받는 사람이 다음과 같음**
  - **받는 사람 도메인**
  - **받는 사람이 다음의 구성원임**

  조건 또는 예외는 한 번만 사용할 수 있지만 조건 또는 예외에 여러 값이 포함될 수 있습니다. 동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_). 다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).

- **우선** 순위: 여러 정책을 만드는 경우 정책이 적용되는 순서를 지정할 수 있습니다. 두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.

  우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>안전한 첨부 파일 정책의 동적 배달

> [!NOTE]
> 동적 배달은 Exchange Online 사서함에만 작동합니다.

안전 첨부 파일 정책의 동적 배달 작업은 안전한 첨부 파일 검색으로 인해 발생할 수 있는 전자 메일 배달 지연을 제거하기 위해 노력합니다. 전자 메일 메시지의 본문은 각 첨부 파일에 대한 자리 표시자가 있는 받는 사람에게 배달됩니다. 첨부 파일이 안전한 것으로 발견될 때까지 자리를 유지한 다음 첨부 파일을 열거나 다운로드할 수 있습니다.

첨부 파일이 악성으로 확인된 경우 메시지는 차단됩니다. 최종 사용자가 아닌 관리자만 안전한 첨부 파일 검색을 통해 확인된 메시지를 검토, 해제 또는 삭제할 수 있습니다. 자세한 내용은 [관리자로 고지된](manage-quarantined-messages-and-files.md)메시지 및 파일 관리를 참조하세요.

안전 첨부 파일 검색이 진행 중일 때 대부분의 PDF 및 Office 문서를 안전 모드에서 미리 볼 수 있습니다. 첨부 파일이 동적 배달 미리 보기와 호환되지 않는 경우 안전한 첨부 파일 검색이 완료될 때까지 받는 사람에게 첨부 파일에 대한 자리 표시자가 표시됩니다.

모바일 장치를 사용 중일 때 PC가 모바일 장치의 동적 배달 미리 보기에서 렌더링되지 않는 경우 모바일 브라우저를 사용하여 웹용 Outlook(이전의 Outlook Web App)에서 메시지를 여어 보십시오.

동적 배달 및 전달된 메시지에 대한 몇 가지 고려 사항은 다음과 같습니다.

- 동적 배달 옵션을 사용하는 안전 첨부 파일 정책에 의해 전달된 받는 사람이 보호되는 경우 받는 사람은 호환되는 파일을 미리 볼 수 있는 자리 표시자가 표시됩니다.

- 전달된 받는 사람이 안전한 첨부 파일 정책으로 보호되지 않는 경우 안전한 첨부 파일 검사 또는 첨부 파일 자리 표시자 없이 메시지와 첨부 파일이 배달됩니다.

동적 배달에서 메시지의 첨부 파일을 바꿀 수 없는 시나리오가 있습니다. 이러한 시나리오는 다음과 같습니다.

- 공용 폴더의 메시지입니다.

- 사용자 지정 규칙을 사용하여 사용자 사서함에서 라우팅된 다음 다시 사용자 사서함으로 라우팅되는 메시지입니다.

- 보관 폴더를 포함하여 클라우드 사서함에서 다른 위치로 자동 또는 수동으로 이동된 메시지입니다.

- 메시지가 삭제되었습니다.

- 사용자의 사서함 검색 폴더가 오류 상태입니다.

- Exclaimer를 사용할 수 있는 Exchange Online 조직 이 문제를 해결하기 위해 [KB4014438을 참조합니다.](https://support.microsoft.com/help/4014438)

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) 암호화된 메시지입니다.

- 안전 첨부 파일 정책에서 동적 배달 작업을 구성했지만 받는 사람이 동적 배달을 지원하지 않습니다(예: 받는 사람이 사내 Exchange 조직의 사서함인 경우). 그러나 [Office 365용 Microsoft Defender의](set-up-safe-links-policies.md) 안전한 링크는 URL이 포함된 Office 파일 첨부 파일을 [](configure-global-settings-for-safe-links.md) 검색할 수 있습니다(안전한 링크에 대한 전역 설정 구성 방법에 따라 다를 수 있습니다).

## <a name="submitting-files-for-malware-analysis"></a>맬웨어 분석을 위한 파일 제출

- 분석을 위해 Microsoft에 보낼 파일을 받으면 분석을 위해 Microsoft에 맬웨어 및 맬웨어가 아닌 [제출을 참조합니다.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)

- 분석을 위해 Microsoft에 제출할 전자 메일 메시지(첨부 파일 포함 또는 포함)를 받으면 Microsoft에 메시지 및 파일 보고를 [참조하세요.](report-junk-email-messages-to-microsoft.md)
