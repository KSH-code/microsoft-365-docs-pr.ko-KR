---
title: 2016에서 Advanced eDiscovery 설정 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사례 만들기 및 관리를 시작할 수 있도록 Advanced eDiscovery 방법을 설명합니다. 또한 필수 Microsoft 구독 및 라이선싱에 대해 설명합니다. 몇 가지 빠른 단계를 완료하면 Advanced eDiscovery 사용할 수 있습니다.
ms.openlocfilehash: cf2d7c6bc770dd6125777c895771b3b61c8ee593
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786965"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>설정 Microsoft 365 Advanced eDiscovery

Advanced eDiscovery 조직의 Microsoft 365 조사에 응답하는 데이터를 보존, 수집, 검토, 분석 및 내보낼 수 있는 종단 간 워크플로를 제공합니다. 조직에서 Advanced eDiscovery 배포할 필요는 없지만 IT 관리자 및 eDiscovery 관리자가 몇 가지 선행 작업을 완료해야 조직에서 Advanced eDiscovery 사례를 만들고 사용하여 조사를 관리할 수 있습니다.

이 문서에서는 설치를 설정하는 데 필요한 다음 단계에 대해 Advanced eDiscovery.

![설치 단계를 Advanced eDiscovery.](../media/set-up-advanced-ediscovery.png)

여기에는 사례에 액세스하고 Advanced eDiscovery 추가하는 데 필요한 적절한 라이선스를 보장하고 사례에 액세스하고 관리할 수 있도록 법률 및 조사 팀에 권한을 할당하는 것이 포함됩니다.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>1단계: 적절한 라이선스 확인 및 할당

라이선스를 Advanced eDiscovery 조직 구독 및 사용자당 라이선스가 필요합니다. 라이선스 요구 사항 목록은 Advanced eDiscovery 및 [라이선싱을 참조하세요.](overview-ediscovery-20.md#subscriptions-and-licensing)

## <a name="step-2-assign-ediscovery-permissions"></a>2단계: eDiscovery 사용 권한 할당

사용자 Advanced eDiscovery 액세스하거나 Advanced eDiscovery 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다. 특히, 사용자를 사용자 계정에서 eDiscovery 관리자 역할 그룹의 구성원으로 Microsoft 365 규정 준수 센터. 이 역할 그룹의 구성원은 이러한 사례를 만들고 관리할 Advanced eDiscovery 있습니다. 구성원을 추가 및 제거하고, 보유자 및 콘텐츠 위치를 보류하고, 법적 보류 알림을 관리하고, 사례에 연결된 검색을 만들고 편집하고, 검토 집합에 검색 결과를 추가하고, 검토 집합의 데이터를 분석하고, Advanced eDiscovery 사례에서 내보내고 다운로드할 수 있습니다.

다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.

1. 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">Microsoft 365 규정 준수 센터</a>조직의 관리자 계정에 대한 자격 증명을 사용하여 Microsoft 365 로그인합니다.

2. 사용 **권한 페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.

3. eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.

4. 역할 그룹 편집 **마법사의 eDiscovery 관리자** 선택 페이지에서 **eDiscovery 관리자 선택을 클릭합니다.**

5. **추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.

6. **추가를** 클릭하여 선택한 사용자를 추가한 다음 완료 를 **클릭합니다.**

7. **저장을** 클릭하여 역할 그룹에 사용자를 추가한  다음 닫기 를 클릭하여 단계를 완료합니다.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>eDiscovery 관리자 역할 그룹에 대한 자세한 정보

eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다. 이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.

- **eDiscovery** 관리자: 만들거나 구성원으로 Advanced eDiscovery 사례를 보고 관리할 수 있습니다. 다른 eDiscovery 관리자가 사례를 만들어 두 번째 eDiscovery 관리자(Manager)를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Advanced eDiscovery 페이지에서 사례를 보거나 열 수 없습니다. 일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.

- **eDiscovery 관리자: eDiscovery** 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.

  - Advanced eDiscovery 페이지에 나열된 모든 케이스 보기
  
  - 본인을 케이스의 구성원으로 추가한 후 조직의 케이스 관리

  - 조직의 케이스에 대한 케이스 데이터 액세스 및 내보내기

  광범위한 액세스 권한으로 인해 조직에는 eDiscovery 관리자 하위 그룹의 구성원인 일부 관리자만 필요합니다.

eDiscovery 사용 권한에 대한 자세한 내용과 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>3단계: 사용자에 대한 전역 Advanced eDiscovery

조직의 사용자가 사례를 만들고 사용하기 전에 완료하는 마지막 단계는 조직의 모든 사례에 적용되는 전역 설정을 구성하는 것입니다. 현재 전역 설정은 *변호사-클라이언트* 권한 검색뿐입니다(향후 더 많은 전역 설정을 사용할 수 있습니다). 이 설정을 사용하면 검토 집합의 데이터를 분석할 때 변호사-클라이언트 권한 모델을 실행할 수 있습니다. 이 모델에서는 기계 학습을 사용하여 문서에 본질적으로 적합한 콘텐츠가 포함되어 있는지 여부를 판단합니다. 또한 문서의 참가자를 변호사 목록과 비교하여(모델을 설정할 때 제출한) 문서에 변호사인 참가자가 한 명 이상 있는지도 파악합니다.

변호사-클라이언트 권한 검색 모델을 설정하고 사용하는 데 대한 자세한 내용은 [Set up attorney-client privilege detection in Advanced eDiscovery.](attorney-privilege-detection.md)

> [!NOTE]
> 이 단계는 언제든지 수행할 수 있는 선택적 단계입니다. 변호사-클라이언트 권한 검색 모델을 구현하지 않는다고 해서 이러한 사례를 만들고 사용할 Advanced eDiscovery 없습니다.

## <a name="next-steps"></a>다음 단계

설치 Advanced eDiscovery 사례를 만들 준비가 된 [것입니다.](create-and-manage-advanced-ediscoveryv2-case.md)