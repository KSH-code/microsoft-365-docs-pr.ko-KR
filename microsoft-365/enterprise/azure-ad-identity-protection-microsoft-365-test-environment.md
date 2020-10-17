---
title: 엔터프라이즈 테스트 환경용 Microsoft 365 Azure AD Id 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365에서 엔터프라이즈 테스트 환경에 대 한 현재 계정을 분석 합니다.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487711"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈 테스트 환경용 Microsoft 365 Azure AD Id 보호

*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*

Azure Active Directory (Azure AD) Id 보호를 사용 하 여 조직의 id에 영향을 주는 잠재적 취약성을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다. 이 문서에서는 Azure AD Id 보호를 사용 하 여 테스트 환경 계정의 분석을 보는 방법을 설명 합니다.

엔터프라이즈 테스트 환경용 Microsoft 365에서 Azure AD Id 보호를 설정 하는 작업은 다음 두 단계로 구성 됩니다.

- [1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2 단계: Azure AD Id 보호 사용](#phase-2-use-azure-ad-identity-protection)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축

최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> Azure AD Id 보호를 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>2 단계: Azure AD Id 보호 사용

1. 브라우저의 개인 인스턴스를 열고 [https://portal.azure.com](https://portal.azure.com) 엔터프라이즈 테스트 환경에 대 한 Microsoft 365의 전역 관리자 계정을 사용 하 여 Azure 포털에 로그인 합니다.
2. Azure portal에서 검색 상자에 **id 보호** 를 입력 한 다음 **Azure AD id 보호**를 선택 합니다.
3. **Id 보호-개요** 블레이드에서 각 보고서를 선택 하 여 보고 되는 내용을 확인 합니다.
4. **알림에서 감지 된 위험에서 사용자** **를 선택 합니다.**
5. **위험 감지 됨 경고** 창에서 **보통**을 선택 합니다.
6. **다음 사용자에 게 전자 메일을 보내는**경우 **포함** 을 선택 하 고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인 합니다.
7. **저장**을 선택합니다.

**보호**에서 다양 한 정책을 선택 하 여 구성 방법을 확인 합니다. 정책을 만들고 활성화 하는 경우에는 모든 사용자에 대 한 액세스를 차단 하지 않는지 또는 로그인 하지 못할 수 있습니다. 이를 방지 하려면 전역 관리자와 같은 특정 사용자 계정을 제외 합니다.

추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[Id 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[엔터프라이즈 설명서에 대 한 Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
