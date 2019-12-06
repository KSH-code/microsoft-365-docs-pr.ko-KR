---
title: FIPS (연방 정보 처리 표준) 게시 140-2
description: Microsoft는 해당 암호화 모듈이 미국 연방 정보 처리 표준을 따르는지 인증 합니다.
keywords: Microsoft 365, 규정 준수, 제품
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 4921fdaa2c6dc7199adb810f5320972f0c1ef8db
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859828"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>FIPS (연방 정보 처리 표준) 게시 140-2

## <a name="fips-140-2-standard-overview"></a>FIPS 140-2 표준 개요

FIPS (연방 정보 처리 표준) 게시 140-2는 정보의 5131 섹션에 정의 된 정보 기술 제품의 암호화 모듈에 대 한 최소 보안 요구 사항을 정의 하는 미국 정부 표준입니다. 기술 관리 개정 1996의 Act입니다.

Nvp ( [암호화 모듈 유효성 검사 프로그램](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) )는 미국 국내 표준 및 기술 (NIST)과 캐나다의 사이버 보안 (cccs)에 대 한 공동 작업으로, 암호화 모듈 표준 (즉, fips 140-2) 및 관련 FIPS 암호화 표준 *에 대 한 보안 요구 사항에 대 한* 암호화 모듈의 유효성을 검사 합니다. FIPS 140-2 보안 요구 사항에는 암호화 모듈의 디자인 및 구현과 관련 된 11 개의 영역이 포함 되어 있습니다. NIST 정보 기술 실험에서는 모듈에서 FIPS로 승인 된 암호화 알고리즘의 유효성을 검사 하는 관련 프로그램을 실행 합니다.

## <a name="microsofts-approach-to-fips-140-2-validation"></a>FIPS 140-2 유효성 검사에 대 한 Microsoft의 접근 방법

Microsoft는 2001에서 표준의 개시 이후로 유효성이 검사 된 암호화 모듈이 있는 140-2 요구 사항을 충족 하기 위한 활성 약정을 유지 관리 합니다. Microsoft는 NIST (표준 및 협회) [암호화 모듈 유효성 검사 프로그램](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (gvp)에서 암호화 모듈의 유효성을 검사 합니다. 많은 클라우드 서비스를 비롯 한 여러 Microsoft 제품이 이러한 암호화 모듈을 사용 합니다.

Microsoft Windows 암호화 모듈, 각 모듈에 대 한 보안 정책 및 NVP 인증서 세부 정보의 카탈로그에 대 한 기술 정보는 [Windows 및 Windows SERVER FIPS 140-2 콘텐츠](https://aka.ms/AA6ehud)를 참조 하세요.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

현재 CMVP FIPS 140-2 구현 지침은 클라우드 서비스 자체에 대 한 FIPS 140-2 유효성 검사를 수행 하지 않습니다. 클라우드 서비스 공급자는 클라우드 서비스를 구성 하는 컴퓨팅 요소에 대해 FIPS 140 유효성 검사 암호화 모듈을 얻고 작동 하도록 선택할 수 있습니다. FIPS 140-2 유효성이 검사 된 구성 요소를 포함 하는 Microsoft online services에는 다음이 포함 됩니다.

- [Azure 및 Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 및 Dynamics 365 정부](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>자주하는 질문

**"FIPS 140 유효성 검사"와 "FIPS 140 준수" 간의 차이점은 무엇입니까?**

"FIPS 140 유효성 검사"는 FIPS 140-2 요구 사항을 충족 하는 것으로 서 NVP에서 모듈을 포함 하는 제품 또는 암호화 모듈 ("인증 된")이 유효한 지를 의미 합니다. "FIPS 140 규격"은 암호화 기능에 대해 FIPS 140 유효성이 검사 된 제품을 사용 하는 IT 제품의 업계 용어입니다.

**Microsoft에서 FIPS 140 유효성 검사를 수행 하는 경우는 언제 입니까?**

모듈 유효성 검사를 시작 하기 위한 흐름은 Windows 10 및 Windows Server의 기능 업데이트에 맞게 정렬 됩니다. 소프트웨어 업계가 발전 함에 따라 운영 체제는 소프트웨어 업데이트를 비롯 하 여 더 자주 출시 됩니다. Microsoft undertakes validation for feature 릴리스에 대 한 유효성 검사를 제외 하 고, 릴리스 간에는 암호화 모듈의 변경 내용을 최소화 합니다.

**FIPS 140 유효성 검사에 포함 된 컴퓨터는 무엇입니까?**

Microsoft는 Windows 10 및 Windows Server를 실행 하는 하드웨어 구성의 대표적인 예에 따라 암호화 모듈의 유효성을 검사 합니다. 환경에서 하드웨어를 사용 하는 경우이 FIPS 140-2 유효성 검사를 수락 하는 일반적인 업계 관행 이며,이는 유효성 검사 프로세스에 사용 되는 샘플과 유사 합니다.

**NIST 웹 사이트에는 많은 모듈이 나열 되어 있습니다. 에이전시에 어떤 것이 적용 되는지 어떻게 알 수 있나요?**

FIPS 140-2를 통해 유효성이 검사 된 암호화 모듈을 사용 해야 하는 경우에는 사용 하는 버전이 유효성 검사 목록에 표시 되는지 확인 해야 합니다. NVP 및 Microsoft는 Windows 시스템에 설치 된 모듈을 식별 하기 위한 지침과 함께 제품 릴리스로 구성 된 유효성이 검사 된 암호화 모듈의 목록을 유지 관리 합니다. 시스템을 준수 하도록 구성 하는 방법에 대 한 자세한 내용은 [windows 및 Windows SERVER FIPS 140-2 콘텐츠](https://aka.ms/AA6ehud)를 참조 하세요.

**인증서에 대 한 "FIPS 모드에서 작동 하는 경우"의 의미**

이 주의 사항은 FIPS 140-2 보안 정책과 일치 하는 방식으로 암호화 모듈을 사용 하기 위해 필요한 구성 및 보안 규칙을 따라야 함을 독자에 게 알립니다. 각 모듈에는 자체 보안 정책, 즉 운영 하는 데 필요한 보안 규칙을 정확 하 게 지정 하 고, 승인 된 암호화 알고리즘, 암호화 키 관리 및 인증 기법을 활용 합니다. 보안 규칙은 각 모듈에 대 한 보안 정책에 정의 됩니다. CMVP를 통해 유효성이 검사 된 각 모듈에 대 한 보안 정책에 대 한 링크를 포함 하 여 자세한 내용은 [Windows 및 Windows SERVER FIPS 140-2 콘텐츠](https://aka.ms/AA6ehud)를 참조 하세요.

**FedRAMP에 FIPS 140-2 유효성 검사가 필요 합니까?**

예, FedRAMP (미 연방 위험 및 권한 부여 관리 프로그램)는 FIPS 유효성 검사 암호화 또는 NSA 승인 된 암호화를 사용 하 여 [NIST SP 800-53 Revision 4](https://nvd.nist.gov/800-53/Rev4/)로 정의 된 제어 기준을 따릅니다 (Mandating [암호화 보호](https://nvd.nist.gov/800-53/Rev4/control/SC-13) 포함).

**Microsoft Azure는 FIPS 140-2를 지 원하는 방법에 대해 설명 합니다.**

Azure는 하드웨어, 상업적으로 사용할 수 있는 운영 체제 (Linux 및 Windows) 및 Azure 관련 버전의 Windows를 조합 하 여 작성 되었습니다. Microsoft SDL ( [보안 개발 수명 주기](https://www.microsoft.com/securityengineering/sdl/) )을 통해, 모든 Azure 서비스는 하이퍼 확장 클라우드에서 작동 하는 동안 fips 140-2의 승인 된 알고리즘을 사용 하므로 데이터 보안을 위해 fips 140-2 승인 알고리즘을 사용 합니다.

**Microsoft의 인증 프로세스에서 FIPS 140-2에 대 한 준수를 사용할 수 있나요?**

FIPS 140-2을 준수 하려면 시스템을 FIPS 승인 모드 (암호화 모듈에서 FIPS 승인 된 알고리즘만 사용)로 실행 하도록 구성 해야 합니다. 시스템을 준수 하도록 구성 하는 방법에 대 한 자세한 내용은 [windows 및 Windows SERVER FIPS 140-2 콘텐츠](https://aka.ms/AA6ehud)를 참조 하세요.

**FIPS 140-2와 일반 조건 간의 관계는 무엇 인가요?**

두 보안 표준은 서로 다르지만 용도가 다릅니다. FIPS 140-2는 소프트웨어 및 하드웨어 암호화 모듈의 유효성 검사를 위해 특별히 설계 되었지만, 일반적인 기준은 IT 소프트웨어 및 하드웨어 제품에서 보안 기능을 평가 하기 위한 것입니다. 일반적인 기준 평가는 대개 FIPS 140-2 유효성 검사를 사용 하 여 기본 암호화 기능이 제대로 구현 된다는 것을 보증 합니다.

## <a name="resources"></a>리소스

- [FIPS Pub 140-2 암호화 모듈에 대 한 보안 요구 사항](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [NIST 암호화 모듈 유효성 검사 프로그램](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows, Windows Server 및 FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>제공 사항의 배경 설명 다운로드

이 제공 사항에 대한 배경 설명 문서가 필요한가요? [PDF](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf)를 다운로드합니다.