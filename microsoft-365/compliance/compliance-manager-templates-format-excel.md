---
title: Microsoft 준수 관리자용 Excel 평가 템플릿 데이터 형식 지정
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자에서 평가 템플릿에 Excel 데이터를 사용하는 방법을 이해합니다.
ms.openlocfilehash: 899dd42401bb4c7acceb1db5bfe5816b383ae16b
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335661"
---
# <a name="format-assessment-template-data-in-excel-for-microsoft-compliance-manager"></a>Microsoft 준수 관리자용 Excel 평가 템플릿 데이터 형식 지정

준수 [](compliance-manager-templates-extend.md) [관리자에서](compliance-manager-templates-create.md)평가 템플릿을 만들거나 수정하거나 확장하는 경우 특정 형식 및 Excel 사용하는 스프레드시트에서 작업하게 됩니다. [](compliance-manager-templates-modify.md) 파일을 올바르게 가져오기 위해 이러한 사양을 따라야 합니다.

## <a name="download-example-spreadsheet"></a>다운로드 예제 스프레드시트

예제 스프레드시트를 보기 위해 예제 [파일 을 다운로드합니다.](https://go.microsoft.com/fwlink/?linkid=2124865) 이 파일을 참조하여 자체 파일을 만들 수 있습니다.

기존 템플릿을 수정하려면 먼저 준수 관리자에서 템플릿 세부 정보를 보고 해당 템플릿의 Excel 다운로드합니다.

## <a name="spreadsheet-format"></a>스프레드시트 형식

Excel 스프레드시트에는 4개의 탭이 포함되어 있습니다. 이 중 3개는 필수입니다.

1. [템플릿(필수)](#template-tab)
2. [ControlFamily(필수)](#controlfamily-tab)
3. [작업(필수)](#actions-tab)
4. [차원(선택](#dimensions-tab) 사항)

스프레드시트를 서식 파일 데이터로 채울 때 스프레드시트에는 위에 나열된 순서대로 탭이 포함되어야 합니다. 그렇지 않으면 데이터를 서식 파일로 가져오지 못합니다.

### <a name="template-tab"></a>서식 파일 탭

서식 **파일 탭이** 필요합니다. 이 탭의 정보는 템플릿에 대한 메타데이터를 제공합니다. 4개의 필수 열이 있습니다. 열은 아래 나열된 Excel 순서를 유지해야 합니다. 4열 다음에  나만의 열을 추가하여 차원을 제공할 수 있습니다. 이렇게 하는 경우 차원 탭에 **추가해야** 합니다.

- **title**: 이 제목은 고유해야 하는 서식 파일 제목입니다. 자체 템플릿 또는 준수 관리자 템플릿을 포함하여 준수 관리자에 있는 다른 템플릿과 이름을 공유할 수 없습니다.

- **product**: 필수 차원입니다. 템플릿과 연결된 제품을 나열합니다.

- **certification**: 템플릿에 사용하는 규정입니다.

- **inScopeServices:** 이 평가에서 다루는 제품 내의 서비스입니다(예: 제품으로 Office 365 나열한 경우 Microsoft Teams 범위 내 서비스일 수 있습니다). 여러 서비스를 세미 콜론으로 구분하여 나열할 수 있습니다.

> [!NOTE]
> 스프레드시트를  가져와서 템플릿을 만들거나 사용자 지정한 후 제품 및 인증 셀에 삽입하는 데이터는 편집할 수 없습니다.  또한 그룹은 **제품/인증** 조합이 동일한 두 개의 평가를 포함할 수 없습니다. 제품/인증 조합이 동일한 여러 템플릿을 사용할 수 있습니다.

### <a name="controlfamily-tab"></a>ControlFamily 탭

**ControlFamily** 탭이 필요합니다.  샘플 스프레드시트에 제공된 순서에 따라야 하는 이 탭의 필수 열은 다음과 같습니다.

- **controlName**: 일반적으로 일종의 ID인 인증, 표준 또는 규정의 컨트롤 이름입니다. 컨트롤 이름은 서식 파일 내에서 고유해야 합니다. 스프레드시트에서 이름이 같은 컨트롤을 여러 개 사용할 수 없습니다.

- **controlFamily**: 컨트롤의 광범위한 그룹을 식별하는 controlFamily에 대한 단어 또는 구를 제공합니다. controlFamily는 고유할 수 없습니다. 스프레드시트에 두 번 이상 나열할 수 있습니다. 서로 관계가 없는 동일한 controlFamily도 여러 템플릿에 나열될 수 있습니다. 모든 controlFamily는 하나 이상의 컨트롤에 매핑되어야 합니다.

- **controlTitle**: 컨트롤의 제목을 제공합니다. controlName은 참조 코드인 반면 제목은 일반적으로 규정에 설명된 서식 있는 텍스트 형식입니다.

- **controlDescription**: 컨트롤에 대한 설명을 제공합니다.

- **controlActionTitle**: 이 필드는 actionTitle에 나열된 하나 이상의 작업에 컨트롤을 관련합니다. 두 개의 세미 콜론으로 구분하여 여러 작업을 추가할 수 있습니다. 나열하는 모든 컨트롤에는 하나 이상의 기존 동작이 포함되어야 합니다. 동작은 동일한 스프레드시트의 **동작** 탭에 정의되거나 다른 템플릿에 포함되거나 Microsoft에서 만들 수 있습니다. 여러 컨트롤이 동일한 작업을 참조할 수 있습니다.

### <a name="actions-tab"></a>작업 탭

작업 **탭이** 필요합니다.  규정 준수 관리자에 이미 있는 Microsoft가 아니라 조직에서 관리하는 개선 작업을 지정합니다. 샘플 스프레드시트에 제공된 순서를 따라야 하는 이 탭에 필요한 열은 다음과 같습니다.

- **actionTitle**: 작업의 제목으로, 필수 필드입니다. 제공하는 제목은 고유해야 합니다. **중요:** 이미 존재하는 작업(예: 다른 템플릿)을 참조하고 후속 열에서 해당 요소를 수정하면 해당 변경 내용이 다른 서식 파일의 동일한 작업으로 전파됩니다.

- **implementationType**: 이 필수 필드에 아래 세 가지 구현 형식 중 하나를 나열합니다.
- **운영** - 조직 시스템, 자산, 데이터 및 직원의 기밀성, 무결성 및 가용성을 보호하기 위해 사용자 및 프로세스가 구현한 작업(예: 보안 인식 및 교육)
- **기술** - 조직 시스템 및 데이터의 기밀성, 무결성 및 가용성을 보호하기 위해 정보 시스템의 하드웨어, 소프트웨어 또는 펌웨어 구성 요소에 포함된 기술 및 메커니즘을 사용하여 완료된 작업(예: 다단계 인증)
- **문서화** - 조직 시스템, 자산, 데이터 및 담당자의 기밀성, 무결성 및 가용성을 보호하는 데 필요한 제어를 수립하고 정의하는 문서화 정책 및 절차를 통해 구현되는 작업(예: 정보 보안 정책)

- **actionScore**: 이 필수 필드에서 작업의 숫자 점수 값을 제공합니다. 값은 1에서 99까지의 정수입니다. 0, null 또는 비워 두면 안 됩니다. 숫자가 높을수록 규정 준수 태세를 개선하는 데 값이 커야 합니다. 아래 이미지는 준수 관리자가 점수가 제어하는 방법을 보여 주며,

  ![준수 관리자는 포인트 값을 제어합니다.](../media/compliance-score-action-scoring.png "준수 관리자가 포인트 값을 제어합니다.")

- **actionDescriptionTitle**: 설명의 제목으로, 필수입니다. 이 설명 제목을 사용하면 여러 템플릿에서 동일한 작업을 수행하고 각 서식 파일에서 다른 설명을 표면화할 수 있습니다.  이 필드는 설명이 참조하는 서식 파일을 명확히 하는 데 도움이 됩니다. 대부분의 경우 이 필드에 만들 서식 파일 이름을 넣을 수 있습니다.

- **actionDescription**: 동작에 대한 설명을 입력합니다. 굵은 텍스트 및 하이퍼링크와 같은 서식을 적용할 수 있습니다. 이 필드는 필수 필드입니다.

- **dimension-Action 목적**: 선택적 필드입니다. 이 도형을 포함하면 헤더에 "dimension-" prefix가 포함되어야 합니다. 여기에 포함된 모든 차원은 준수 관리자에서 필터로 사용하며 준수 관리자의 개선 작업 세부 정보 페이지에 표시됩니다.

### <a name="dimensions-tab"></a>차원 탭

차원 **탭은** 선택 사항입니다. 그러나 다른 곳에서 차원을 참조하는 경우 이미 만든 서식 파일이나 Microsoft 서식 파일에서 차원이 없는 경우 여기에서 지정해야 합니다. 이 탭의 열은 다음과 같습니다.

- **dimensionKey**: "제품", "인증", "작업 목적"으로 목록
- **dimensionValue**: 예: Office 365, HIPPA, 예방용, 감지용

기존 템플릿을 내보낼 때 내보낼 스프레드시트에는 서식 파일에서 사용되는 모든 차원이 나열되는 차원 탭이 있습니다. 
