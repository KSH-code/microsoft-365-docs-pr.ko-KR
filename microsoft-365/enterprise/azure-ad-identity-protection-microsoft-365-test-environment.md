---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호
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
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 Enterprise 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633646"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호

*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*

Azure Active Directory (Azure AD) Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다. 이 문서에서는 Azure AD Id 보호를 사용 하 여 테스트 환경 계정의 분석을 보는 방법을 설명 합니다.

Microsoft 365 Enterprise 테스트 환경에서 Azure AD Id 보호를 설정 하는 데는 두 가지 단계가 있습니다.

1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2. Azure AD Id 보호를 사용 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> Azure AD Id 보호를 테스트 하는 경우 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>2 단계: Azure AD Id 보호 사용

1. 브라우저의 개인 인스턴스를 열고 Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure 포털에 로그인 합니다.
2. Azure portal에서 검색 상자에 **id 보호** 를 입력 하 고 **Azure AD id 보호**를 클릭 합니다.
3. **Id 보호-개요** 블레이드에서 각 보고서를 클릭 하 여 보고 되는 내용을 확인 합니다.
4. **알림에서 감지 된 위험에 사용자** **를 클릭**합니다.
5. **위험 감지 됨 경고** 창에서 **보통**을 선택 합니다.
6. **다음 사용자에 게 전자 메일을 보내는**경우 **포함** 을 클릭 하 고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인 합니다.
7. **저장**을 클릭합니다.

**보호** 에서 각 정책을 클릭 하 여 구성 방법을 확인 합니다. 정책을 만들고 활성화 하는 경우에는 조건의 범위가 너무 광범위 하 게 액세스를 차단 하지 않도록 하거나 전역 관리자 인 로그인을 하지 못할 수도 있습니다.

추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.

프로덕션 환경에서 Azure AD Id 보호를 배포 하는 방법에 대 한 자세한 내용은 Id 단계의 [자격 증명 손상 보호](identity-secure-user-sign-ins.md#identity-ident-prot) 단계를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
