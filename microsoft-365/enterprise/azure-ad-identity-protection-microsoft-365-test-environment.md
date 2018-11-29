---
title: Azure AD Id 보호 Microsoft 365 기업에 대 한 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 기업 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869803"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Id 보호 Microsoft 365 기업에 대 한 테스트 환경

Azure AD Id 보호를 사용 하면 조직의 id가 영향을 줄 수 있는 잠재적인 취약점 검색, 자동된 응답을 구성 하 고, 문제를 조사할 수 있습니다. 이 문서에서는 Azure AD Id 보호를 설정 하 고 테스트 환경 계정의 분석을 볼 하는 방법에 설명 합니다.

Microsoft 365 기업 테스트 환경에서 Azure AD Id 보호를 설정 하는 두 단계로 가지가 있습니다.

1. Microsoft 365 Enterprise 테스트 환경을 만듭니다.
2. 사용 하도록 설정 하 고 Azure AD Id 보호를 사용 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 Azure AD Id 보호를 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.
  
> [!NOTE]
> Azure AD Id 보호를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공 되 Azure AD Id 보호를 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>2 단계:을 설정 하 고 Azure AD Id 보호를 사용 하 여

1. 브라우저의 개인 인스턴스를 열고에서 Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 사용 합니다.
2. Azure 포털에서 클릭 **모든 서비스 > 마켓플레이스**합니다.
3. **Azure AD Id 보호** 를 입력 하 고을 클릭 합니다.
4. **시작** 블레이드에서 **설정**아래에서 **온보드** 를 클릭 하 **대시보드에 고정을**클릭 한 다음 **만들기**를 클릭 합니다.
5. Azure 포털에서 대시보드에서 **Azure AD Id 보호** 를 클릭 합니다. 

   대시보드로 **Azure AD Id 보호 개요** 블레이드가 표시 됩니다. **취약점**다단계 인증 등록 하지 않고 사용자 계정 수를 결정 되도록를 확인 합니다. 이 번호는 이전 Microsoft 365 Enterprise 테스트 랩 가이드를 수행한 상태 여야에 따라 달라 집니다.

6. **조사** 를 모든 사용자 또는 검색 된 이벤트 참조에 대 한 범주를 통해이 옵션을 클릭 합니다.

추가 테스트 및 실험 [Simulating 위험 이벤트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하십시오.

정보 및 프로덕션 환경에서 Azure AD Id 보호를 배포에 대 한 링크에 대 한 Identity 단계에서 [손상 암호로 보호 자격 증명에 대 한](identity-azure-ad-identity-protection.md) 단계를 참조 하십시오.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[2단계: ID](identity-infrastructure.md)

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 엔터프라이즈 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
