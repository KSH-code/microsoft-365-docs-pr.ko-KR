---
title: 365 Windows 클라우드 PC 설정 문제 해결
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
description: 365 Business 클라우드 PC의 설치 문제를 Windows 방법을 학습합니다.
ms.date: 08/13/2021
ms.openlocfilehash: 701d1ce3ae97836d6687050e16a176aad85e2995
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192102"
---
# <a name="troubleshoot-windows-365-business-cloud-pc-setup-issues"></a>365 Windows 클라우드 PC 설정 문제 해결

사용자에게 "설치 실패" 오류가 발생하거나 라이선스를 할당한 후 90분보다 오래 걸리는 경우 이 문서의 단계를 사용하여 문제를 해결합니다.

> [!IMPORTANT]
> 이 문서에 설명된 대부분의 작업을 수행하려면 전역 관리자 되어야 합니다. 특정 절차에 다른 관리자 역할을 사용할 수 있는 경우 절차 전에 해당 역할에 대해 설명됩니다. Azure Portal의 일부에 로그인하거나 액세스할 수 있는 권한이 없는 경우 IT 관리자에게 문의하세요. Azure 규칙에 대한 자세한 내용은 Azure AD 기본 [제공 역할을 참조하세요.](/azure/active-directory/roles/permissions-reference) Azure Portal에 대한 자세한 내용은 [Azure Portal 개요를 참조하세요.](/azure/azure-portal/azure-portal-overview)

## <a name="step-1-verify-azure-ad-device-settings"></a>1단계. Azure AD 장치 설정 확인

사용자가 **장치를 Azure AD에 가입할** 수 있는지 확인이 모두 로 설정되어 **있는지 확인**

1. 에서 Microsoft Azure 포털에 [https://portal.azure.com/](https://go.microsoft.com/fwlink/p/?linkid=516942) 로그인합니다.
2. 관리 **Azure Active Directory** **보기를 선택합니다.**
3. 왼쪽 nav의 관리 에서 장치 **를** 선택한 다음 장치 설정을 **선택합니다.**
4. 사용자가 **장치를 Azure AD에** 가입할 수 있는 경우 모두로 설정되지 **않은** 경우 모두 를 선택한 다음 저장을 **선택합니다.**
5. [2단계로 이동. 365 Windows](#step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active)영구 사용자 시스템 계정이 활성 상태인지 확인

## <a name="step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active"></a>2단계. Windows 365 BPRT 영구 사용자 시스템 계정이 활성 상태인지 확인

조직에서 Windows 365 라이선스를 처음 할당하면 Azure AD에서 Windows **BPRT** 영구 사용자라는 시스템 계정이 자동으로 만들어집니다. 이 계정을 삭제하거나 변경하지 않습니다(예: 이름 또는 UPN 변경). 시스템 계정을 수정하거나 삭제하면 설치가 실패합니다. 이 시스템 계정은 원활한 설치 프로세스를 보장하며, Windows 365 Business의 범위가 지정되는 서비스 기능 이외에는 조직에 대한 쓰기 기능이나 액세스 권한이 없습니다. 이 시스템 계정을 삭제하거나 수정하는 경우 windows365.microsoft.com 365 Business 라이선스가 Windows 계정으로 로그인하고 토큰이 새로 고쳐지기까지 12시간을 기다려야 합니다.

Azure AD에서 Windows 365 BPRT 영구 사용자 시스템 계정이 활성화되어 있는지 확인하려면 다음 단계를 수행합니다.

1. Azure Portal에서 서비스 개요 <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">Azure Active Directory 이동합니다.</a>
2. 왼쪽 nav의 **관리에서** 사용자를 **선택합니다.**
3. 검색 상자에 Windows **365 BPRT 영구** 사용자 를 입력한 다음 Enter 를 **입력합니다.**
4. 365 Windows 영구 사용자 시스템 계정이 있는 경우 [3단계로 이동하세요. 장치 기반 MFA가 꺼져 있는지 확인합니다.](#step-3-verify-that-device-based-mfa-is-turned-off)
5. Windows 365 BPRT 영구 사용자 시스템 계정이 누락되거나 변경된 경우 windows365.microsoft.com 365 Business 라이선스가 할당된 계정으로 Windows 로그인합니다. 365 BPRT 영구 Windows 새 계정이 12시간 후 생성됩니다. 토큰이 다시 생성된 후 [6단계로 직접 이동 합니다. 클라우드 PC를 초기화합니다.](#step-6-reset-your-cloud-pcs)

## <a name="step-3-verify-that-device-based-mfa-is-turned-off"></a>3단계. 장치 기반 MFA가 꺼져 있는지 확인

Azure AD를 사용하여 디바이스를 가입하는 데 MFA(Multi-Factor Authentication)가 필요하도록 조직을 구성할 수 있습니다. 이 경우 이 설정을 해제해야 합니다. **Azure AD를** 사용하여 디바이스를 등록하거나 가입하려면 다단계 인증 필요를 **아니요로 설정하려면** 다음 단계를 수행합니다.

1. Azure Portal에서 서비스 개요 <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">Azure Active Directory 이동합니다.</a>
2. 왼쪽 nav의 관리 에서 장치 **를** 선택한 다음 장치 설정을 **선택합니다.**
3. **Azure AD를 사용하여** 장치를 등록하거나 가입하기 위해 다단계 인증 필요를 **예로** 설정한 경우 아니요 **,** 저장을 **선택합니다.**
4. [4단계로 이동 MFA가 설치를 차단하지 않는지 확인](#step-4-make-sure-that-mfa-doesnt-block-setup)

## <a name="step-4-make-sure-that-mfa-doesnt-block-setup"></a>4단계. MFA가 설치를 차단하지 않는지 확인

조건부 액세스를 포함하는 Azure AD Premium P1 라이선스가 없는 경우 [5단계로 이동 합니다. MDM](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)기관 구성이 올바르게 설정되어 있는지 확인합니다. 구독에 구독이 포함되어 있는지 여부를 모르는 Azure AD Premium P1 어떤 [구독이 있나요?를 참조하세요.](../admin-overview/what-subscription-do-i-have.md)

조건부 액세스가 포함된 Azure AD Premium P1 라이선스가 있는 경우 이 문서의 나머지 단계를 완료한 후 첫 번째 사용자로 Windows 365 홈페이지에 로그인할 사용자를 [https://windows365.microsoft.com](https://windows365.microsoft.com) 하나 선택합니다. 첫 번째 사용자에 대한 MFA 조건부 액세스 정책이 없는지 확인 설치 시도 중에 MFA는 꺼져 있어야 합니다. 조직 전체에서 모든 클라우드 PC가 성공적으로 설정된 후 이 사용자에 대해 MFA를 설정할 수 있습니다. 조건부 액세스 정책에 대한 자세한 내용은 조건부 [액세스란?을 Azure Active Directory.](/azure/active-directory/conditional-access/overview)

조건부 액세스 정책을 확인하기 위해 다음 단계를 수행합니다.

1. Azure Portal에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2169290" target="_blank">조건부 액세스 정책 페이지로</a> 이동합니다.
2. 정책이 나열되지 않은 경우 [5단계를 계속 진행합니다. MDM](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)기관 구성이 올바르게 설정되어 있는지 확인합니다.
3. 페이지에 정책이 나열되어 있는 경우 정책 이름을 선택합니다.
4. 액세스 **제어 섹션의** **부여에서**"0개 컨트롤이 선택되었습니다."라고 표시되면 정책 목록으로 돌아가 다음 정책을 선택합니다. 그렇지 않은 경우 5단계를 계속 진행합니다.
5. 액세스 **컨트롤 섹션의** 부여에서 두 개 이상의 컨트롤이 선택되어 있는 경우 **_n개_** 컨트롤 선택 링크를 선택합니다. 
6. 오른쪽 창에서 다단계  인증 필요를 선택한 경우 확인란의 선택을 취소한 다음 선택 **단추를** 선택합니다.
   > [!TIP]
   > 또는 정책에서 첫 번째 사용자를 제외할 수 있습니다. 이 작업을 하는 방법에 대한 자세한 내용은 조건부 액세스 [정책에서 제외된 사용자 관리를 참조합니다.](/azure/active-directory/governance/conditional-access-exclusion)
7. 모든 조건부 액세스 정책에 대해 MFA를 제거할 때까지 3-6단계를 반복합니다.
8. [5단계로 이동 MDM](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)기관 구성이 올바르게 설정되어 있는지 확인합니다.

## <a name="step-5-make-sure-mdm-authority-configuration-is-set-up-correctly"></a>5단계. MDM 기관 구성이 올바르게 설정되어 있는지 확인

이 문서 앞부분의 1~4단계를 기준으로 변경한 경우 근본 원인이 해결될 수 있습니다. 문제가 해결되어 있는지 확인을 위해 [6단계로 이동하여 문제를 해결합니다. 클라우드 PC를 초기화합니다.](#step-6-reset-your-cloud-pcs)

1~4단계를 변경하지 않은 경우 환경의 MDM 기관 구성으로 인해 설치가 실패한 것일 수 있습니다. 그렇다면 클라우드 PC를 관리하는 데 사용할 계획인지 여부에 따라 Microsoft Intune 경로가 있습니다.

- 클라우드 PC에 Microsoft Intune 또는 클라우드 PC를 사용하려면 [경로 A: 이동성(MDM 및 MAM)](#path-a-use-microsoft-intune-to-manage-your-cloud-pcs)설정이 올바르게 구성되어 있는지 확인의 단계를 따릅니다.
- 클라우드 PC를 관리하기 위해 Microsoft Intune 계획하지 않는 경우 경로 B: 자동 [MDM 등록 끄기의 단계를 따르세요.](#path-b-turn-off-automatic-mdm-enrollment)

### <a name="path-a-use-microsoft-intune-to-manage-your-cloud-pcs"></a>경로 A. Microsoft Intune 사용하여 클라우드 PC 관리

이미 Microsoft Intune 또는 이를 사용하여 Windows 365 클라우드 PC를 관리하려면 Azure AD의 **모바일(MDM 및 MAM)** 설정이 올바르게 구성되어 있는지 확인합니다.

1. Azure Portal에서 서비스 개요 <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">Azure Active Directory 이동합니다.</a>
2. 왼쪽 네비게이트의 관리에서 모바일(MDM 및 **MAM)을** 선택하고 를  **Microsoft Intune.**
3. 구성 **페이지에서** **MDM** 사용자 범위 옆의  일부 또는 **모두를** 선택한 다음 저장을 **선택합니다.**
4. 왼쪽 네비게이트의 관리에서 모바일(MDM 및  **MAM)을** 선택하고 Microsoft Intune 등록을 선택한 다음 3단계를 반복합니다. 

클라우드 PC가 할당된 사용자에게는 Intune 라이선스가 할당되어 있어야 합니다. CloudPCBPRT 시스템 계정에 Intune 라이선스를 할당할 필요가 없습니다.

> [!IMPORTANT]
> 라이선스를 할당하려면 전역 관리자 또는 라이선스 관리자 또는 라이선스 권한이 있는 역할이 있어야 합니다.

1. Microsoft Endpoint Manager [관리 센터에서](https://go.microsoft.com/fwlink/p/?linkid=2169290)사용자 모든   >  **사용자를 선택합니다.**
2. 모든 **사용자 목록에서** 사용자를 선택합니다.
3. 사용자 프로필 **페이지에서** 라이선스 **를 선택합니다.**
4. 라이선스 **페이지에서** 할당 **을 선택합니다.**
5. **Intune을 찾은** 다음 확인란을 선택한 다음 저장을 **선택합니다.** 이제 사용자 계정에 서비스를 사용하여 장치를 등록하는 데 필요한 권한이 있습니다.
6. [6단계로 이동 클라우드 PC를 초기화합니다.](#step-6-reset-your-cloud-pcs)

### <a name="path-b-turn-off-automatic-mdm-enrollment"></a>경로 B. 자동 MDM 등록 끄기

클라우드 PC 관리에 Microsoft Intune 사용하지 않는 경우 자동 MDM 등록을 해제해야 합니다.

> [!IMPORTANT]
> MDM 관리자가 아닌 경우 먼저 IT 관리자와 상의하지 않고 다음 절차 중 하나를 사용하지 않습니다. 클라우드 PC를 설정하지 않는 경우 다음 절차를 따르기만 합니다. 구성을 변경하면 관리 환경에 영향을 줄 수 있습니다. 도움이 필요한 경우 [Intune 지원에 문의합니다.](/mem/get-support)

#### <a name="use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment"></a>Azure AD 포털을 사용하여 자동 Intune 등록 끄기

1. Azure Portal에서 서비스 개요 <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">Azure Active Directory 이동합니다.</a>
2. 왼쪽 네비게이트의 관리에서 모바일(MDM 및 **MAM)을** 선택하고 를  **Microsoft Intune.**
3. 구성 **페이지에서** 두 가지 중 하나를 볼 수 있습니다. 구독이 Azure AD Premium MDM 사용자  범위 옆의 없음을 선택한 다음 저장을 **선택합니다.** 구독이 없는 경우 Azure AD Premium 사용 안 **을 선택합니다.**
4. 왼쪽 네비게이트의 관리에서 모바일(MDM 및  **MAM)을** 선택하고 Microsoft Intune 등록을 선택한 다음 3단계를 반복합니다. 
5. [6단계로 이동 클라우드 PC를 초기화합니다.](#step-6-reset-your-cloud-pcs)


## <a name="step-6-reset-your-cloud-pcs"></a>6단계. 클라우드 PC 초기화

이 문서의 문제 해결 단계를 완료한 후 사용자는 클라우드 PC 설정을 다시 시작해야 합니다. 

3단계를 [완료한 경우 장치 기반 MFA가](#step-3-verify-that-device-based-mfa-is-turned-off)꺼져 있는지 확인합니다. 변경 내용이 적용될 때까지 10분 이상 기다린 후 계속 진행합니다. MFA에서 제외한 사용자가 [365 365](https://windows365.microsoft.com)홈 페이지에 처음 로그인하는 Windows 있는지 확인하십시오.

"설치가 실패했습니다." 오류가 표시된 모든 클라우드 PC 사용자에게 다음 단계에 따라 클라우드 PC를 초기화할 수 있도록 합니다.

1. Windows [365](https://windows365.microsoft.com)홈페이지에서 "설치 실패" 상태가 있는 클라우드 PC의 기어 아이콘을 선택한 다음 초기화 를 **선택합니다.** 이 작업을 수행하면 설치 프로세스가 다시 시작됩니다.
2. 재설정 후 "설치에 실패했습니다." 오류가 계속 표시되면 [5단계를 건너뜁니다. MDM](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)기관 구성이 올바르게 설정되어 있는지 확인합니다. 이 단계를 완료한 다음 CloudPC를 다시 초기화합니다. 그렇지 않은 경우 왼쪽 검색  창에서 새 지원 요청을 선택하여 지원 티켓을 열 수 있습니다.
