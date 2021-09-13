---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스에 대한 추가 장치 정보입니다.'
ms.openlocfilehash: b38c279bbbb763c8f0859d6d45cd838c8652ec5e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191259"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션하기 위한 추가 장치 정보

도이치클랜드 Microsoft 클라우드에 연결된 Azure AD 가입 및 등록된 장치는 9단계 및 10단계 이전으로 마이그레이션해야 합니다. 디바이스의 마이그레이션은 장치 유형, 운영 체제 및 Azure AD 관계에 따라 다릅니다.

## <a name="azure-ad-joined-windows-10-devices"></a>Azure AD 가입 Windows 10 장치
Azure Windows 10 디바이스가 연결된 경우 Azure AD에서 연결을 끊고 다시 연결해야 합니다.

[![Azure AD 장치 Re-Join Flow. ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


사용자가 Windows 10 디바이스의 관리자인 경우 사용자는 Azure AD에서 디바이스 등록을 등록을 해지하고 3단계로 다시 등록할 수 있습니다.

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>1단계: 디바이스가 Azure ID에 가입된지 확인

1. 회사 계정으로 로그인합니다.
2. 계정 **설정**  >    >  **또는 학교 액세스로 이동하십시오.**
3. **목록에서 [...]에 연결된 계정을 찾아야 합니다. s Azure AD**.
4. 연결된 계정이 있는 경우 2단계를 진행합니다.

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>2단계: Azure AD에서 장치 연결 끊기

1. 연결된 **직장** 또는 학교 계정에서 연결 끊기를 클릭합니다.
2. 연결이 끊어진 것을 두 번 확인 합니다.
3. 로컬 관리자 사용자 이름과 암호를 입력합니다. 디바이스의 연결이 끊어집니다.
4. 장치를 다시 시작합니다.

### <a name="step-3-join-the-device-to-azure-ad"></a>3단계: 디바이스를 Azure AD에 연결

1. 로컬 관리자의 자격 증명으로 로그인합니다.
2. 계정 **설정**  >    >  **또는 학교 액세스로 이동하십시오.**
3. **연결** 을 클릭합니다.
4. **중요:** **Azure AD에 가입을 클릭합니다.**
5. 직장 계정의 전자 메일 주소와 암호를 입력합니다. 장치가 연결되어 있습니다.
6. 장치를 다시 시작합니다.
7. 직장 계정의 전자 메일 주소와 암호로 로그인합니다.

사용자가 디바이스 관리자가 아닌 경우 Azure **AD DC** **관리자,** 클라우드 응용  프로그램 관리자 또는 전역 관리자는 이 구성 경로에 따라 디바이스에서 로컬 관리자 계정을 만들고 디바이스에 연결을 해지할 수 있습니다.

*설정 > 계정 > Microsoft > 없는 사용자 > > 자격 증명을 사용할 수 없음*

자세한 내용은 [관리자 역할 정보](/microsoft-365/admin/add-users/about-admin-roles?)를 참조하세요.

다시 연결하기 위해 이 단계에서 조직의 모든 작업 계정의 자격 증명을 사용할 수 있습니다.

디바이스에 가입하는 데 사용되는 작업 계정이 장치의 관리자로 자동 승격됩니다.
조직의 다른 모든 작업 계정은 장치에 로그인할 수 있지만 관리자 권한이 없습니다.

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure AD 등록(회사 가입) Windows 10 장치

Azure Windows 10 등록된 경우 Azure AD에서 연결을 끊고 다시 연결해야 합니다.

[![Azure AD 장치 Re-Registration Flow. ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>1단계: 장치가 Azure ID로 등록되어 있는지 확인

1. 사용자와 함께 로그인합니다.
2. 계정 **설정**  >    >  **또는 학교 액세스로 이동하십시오.**
3. 목록에서 직장 계정을 검색하고 [...]에 연결되어 있는지 **확인 s Azure AD**.

    직장 계정이 목록에 있지만 Azure AD에 연결되지 않은 경우 2단계를 진행합니다.

    그렇지 않으면 디바이스가 Azure AD 가입 장치이기 때문에 Azure AD 가입 장치 를 [Windows 10 합니다.](#azure-ad-joined-windows-10-devices)

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>2단계: Azure AD에서 장치 연결 끊기

1. 작업 계정을 클릭합니다. 정보 및 *연결 끊기* *단추가* 나타납니다.
2. 연결 **끊기를 클릭합니다.**
3. 예를 클릭하여 장치에서 계정 제거를 **확인합니다.**

### <a name="step-3-connect-the-device-to-azure-ad"></a>3단계: 커넥트 Azure AD에 연결

1. **연결** 을 클릭합니다.
2. 직장 계정의 전자 메일 주소를 입력하고 다음 을 **클릭합니다.**
3. 직장 계정의 암호를 입력하고 **로그인을 클릭합니다.**
4. 완료 를 클릭하여 **확인** 직장 계정이 다시 나열됩니다.

## <a name="android"></a>Android

Android의 경우 사용자는 장치를 등록을 하지 않은 후 다시 등록해야 합니다. 이 완료는 앱 앱 또는 Microsoft Authenticator 앱을 통해 회사 포털 있습니다.

- Microsoft Authenticator 앱에서 사용자는 장치 **등록으로 설정 > 수 있습니다.** 이 경우 사용자는 디바이스 등록을 등록을 다시 등록하고 다시 등록할 수 있습니다.

- 사용자가 회사 포털 탭으로 **이동하여** 디바이스를 제거할 수 있습니다. 그런 다음 디바이스를 사용하여 장치를 다시 회사 포털.

- 또한 사용자는 계정 설정 페이지에서 계정을 제거한 다음 직장 계정을 읽어 등록을 다시 등록 및 다시 등록할 수 있습니다.

앱 앱을 사용하여 Android에서 디바이스 등록을 등록을 Microsoft Authenticator:

1. 앱 Microsoft Authenticator 열고 으로 **설정.**
2. 장치 **등록 을 선택합니다.**
3. 등록을 다시 등록하지 않습니다.를 선택하여 디바이스 **등록을 등록을 하세요.**
4. 장치 **등록의** 경우 전자 메일 주소를 입력하여 장치를 다시 등록한 다음 등록을 **선택합니다.**

Android 장치 등록을 등록을 해지하고 Android 디바이스를 다시 등록하려면 설정:

1. 장치 **설정** 열고 계정으로 **이동하세요.**
2. 다시 등록할 직장 계정을 선택하고 계정 제거 **를 선택합니다.**
3. 계정이 제거된 후  계정 페이지에서 계정 추가 계정 > **선택합니다.**
4. Workplace **Join의** 경우 전자 메일 주소를 입력하고 **가입을** 선택하여 장치 등록을 완료합니다.

Android에서 디바이스 등록을 해지하고 디바이스를 다시 등록하려면 다음을 회사 포털.

1. 시작 회사 포털 및 장치 **탭으로** 이동 합니다.
2. 장치를 선택하여 장치 세부 정보를 확인합니다.
3. 타원(세 점) 메뉴에서 장치 제거를 선택하고 대화 상자에서 확인하여 제거를 완료합니다. 
4. 이제 앱에 로그아웃해야 회사 포털 있습니다. 로그인을 **선택하여** 장치를 다시 등록합니다.

이 작업의 마이그레이션 단계 중에 필요한 작업 또는 관리 또는 사용에 미치는 영향에 대한 자세한 내용은 도이치랜드에서 마이그레이션을 위한 추가 Azure AD 정보의 Azure Active Directory(Azure AD)에 대한 정보를 [검토하세요.](ms-cloud-germany-transition-azure-ad.md)

## <a name="ios"></a>iOS

iOS 장치에서는 캐시된 계정을 장치에서 수동으로 제거하고, Microsoft Authenticator 등록을 해지하고, 장치의 모든 네이티브 앱에서 로그인해야 합니다.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>1단계: 있는 경우 앱의 Microsoft Authenticator 제거

1. 앱 앱의 계정을 Microsoft Authenticator 탭합니다.
2. 오른쪽 **설정** 아이콘을 탭합니다. if you don't see the **설정,** you might not using the latest version of Microsoft Authenticator.
3. 계정 **제거 단추를** 탭합니다.
4. 이 **디바이스의 모든 앱을 탭합니다.**

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>2단계: Microsoft Authenticator 앱에서 디바이스 등록을 Microsoft Authenticator

1. 오른쪽 위 모서리에서 메뉴 아이콘을 탭합니다.
2. 를 **설정** 다음 **장치 등록 을 탭합니다.**
3. 계정이 표시될 경우 **등록을** 하지 않은 장치 및 대화 상자에서 **계속을** 탭합니다. 그 이후에는 계정이 없습니다.

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>3단계: 필요한 경우 개별 앱에서 서명

사용자는 앱, 앱 Outlook, Teams 및 OneDrive 앱으로 이동하고 해당 앱에서 계정을 제거할 수 있습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**조직이 영향을 받는지 어떻게 알 수 있나요?**

관리자는 Azure AD가 등록되어 있는지 또는 Azure AD에 가입되어 `https://portal.microsoftazure.de` 있는지를 확인해야 합니다. 조직에 Azure AD가 등록되거나 Azure AD 가입 장치가 있는 경우 조직은 이 페이지의 지침을 따라야 합니다.

**사용자가 언제 장치를 다시 등록하나요?**

[9단계가](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 완료된 후에만 장치를 등록을 등록을 해지하고 다시 등록하는 것은 성공에 중요합니다. 10단계가 시작되기 전에 다시 등록을 완료해야 합니다. 그렇지 않으면 장치에 대한 액세스 권한이 손실될 수 있습니다.

**모든 장치가 공용 클라우드에 등록되어 있는 것을 어떻게 알 수 있나요?**

장치가 공용 클라우드에 등록되어 있는지 확인하려면 Azure AD 포털에서 장치 목록을 내보내고 앱 스프레드시트로 Excel 합니다. 그런 다음 조직에서 마이그레이션 프로세스의 9단계를 통과한 날짜 이후에 _registeredTime_ 열을 사용하여 등록된 장치를 [필터링합니다.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)

**아직 Dns 기반 DNS를 사용하여 Microsoft용 DNS 레코드 만들기에 Windows [DNS 이름을 추가해야 하나요?](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)**

이 DNS 항목은 더 이상 장치를 다시 등록할 필요가 없습니다. 

## <a name="additional-considerations"></a>추가 고려 사항

> [!IMPORTANT]
> Intune 서비스 주체는 Azure AD 장치 등록의 활성화를 암시하는 마이그레이션 [프로세스의 3단계](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)후에 활성화됩니다. 마이그레이션 전에 Azure AD 장치 등록을 차단한 경우 Azure AD 포털에서 Azure AD 장치 등록을 다시 사용하지 않도록 설정하려면 PowerShell을 사용하여 Intune 서비스 계정을 사용하지 않도록 설정해야 합니다. 이 명령을 사용하여 Intune 서비스 주체는 Azure Active Directory PowerShell for Graph 있습니다.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)
