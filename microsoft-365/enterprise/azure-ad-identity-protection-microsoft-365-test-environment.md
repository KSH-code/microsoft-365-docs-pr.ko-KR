---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 Enterprise 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: 97530dcec9c32882bbe3b66eb53eaa6d4668a838
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071717"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호

Azure AD Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다. 이 문서에서는 Azure AD Id 보호를 사용 하도록 설정 하 고 테스트 환경 계정에 대 한 분석을 보는 방법을 설명 합니다.

Microsoft 365 Enterprise 테스트 환경에서 Azure AD Id 보호를 설정 하는 데는 두 가지 단계가 있습니다.

1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2. Azure AD Id 보호를 사용 하도록 설정 하 고 사용 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> Azure AD Id 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>2 단계: Azure AD Id 보호 사용 및 사용

1. 브라우저의 개인 인스턴스를 열고 Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure 포털에 로그인 합니다.
2. Azure portal에서 **모든 서비스 >** 을 클릭 합니다.
3. **AZURE AD Id 보호** 를 입력 한 다음 클릭 합니다.
4. **시작** 블레이드에서 **설정**아래의 **온보드** 를 클릭 하 고 **대시보드에 고정**을 클릭 한 다음 **만들기**를 클릭 합니다.
5. Azure portal에서 대시보드의 **AZURE AD Id 보호** 를 클릭 합니다. 

   대시보드의 **AZURE AD Id 보호-개요** 블레이드에서 볼 수 있습니다. **취약성**에 따라 다단계 인증 등록이 없는 사용자 계정 수를 확인 했습니다. 이 숫자는 이전에 수행한 Microsoft 365 Enterprise 테스트 랩 가이드에 따라 달라 집니다.

6. **조사** 를 위해 범주를 클릭 하 여 검색 된 사용자 또는 이벤트가 있는지 확인 합니다.

추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.

프로덕션 환경에서 Azure AD Id 보호를 배포 하는 방법에 대 한 자세한 내용은 Id 단계의 [자격 증명 손상 보호](identity-secure-user-sign-ins.md#identity-ident-prot) 단계를 참조 하세요.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
