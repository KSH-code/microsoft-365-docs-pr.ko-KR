---
title: Windows 작업을 자동화할을 사용 하 여 새 장치에 대 한 Windows 10 엔터프라이즈 배포
description: 구성 하 고 Windows 작업을 자동화할와 Windows 10 엔터프라이즈 배포에 대 한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise Microsoft 365 설명서, Windows 10 엔터프라이즈 배포 Windows 작업을 자동화할
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: ed3d21091acd5b54dfdc2917fca85ed0535c3332
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869969"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>3 단계: Windows 작업을 자동화할을 사용 하 여 새 장치에 대 한 Windows 10 엔터프라이즈 배포

*Microsoft 365 Enterprise의 E3와 e 5 버전에 적용 하는이 문서*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

새 Windows 10 Pc를 사용 하는 경우에 조직에는 out (영문)--상자-체감 oobe (첫 실행)를 사용자 지정 및 앱 및 이미 구성 된 설정을 사용 하 여 새 시스템을 배포 하려면 Windows 작업을 자동화할을 사용할 수 있습니다. 없는 이미지 배포를, 넣기, 수 있는 드라이버가 및 관리할 수 없는 인프라 있습니다. 사용자 수를 통과 하지 배포 프로세스 독립적으로 필요 없이 자신의 IT 관리자에 게 문의 합니다.

설정 하 고 및 사전 새 Windows 10 장치를 구성 하 고, 사용 하도록 준비 작업을 자동화할 Windows를 사용 하 여 생산성을 사용할 수 있습니다. Windows 작업을 자동화할, 이점 및 Windows 작업을 자동화할 시나리오를 포함 하는 방법에 대 한 자세한 내용은 [개요 (영문)의 Windows 작업을 자동화할](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)를 참조 하십시오. 준비가 되 면 따라 새 장치를 설정 하려면 다음 부분으로이 이루어집니다.

## <a name="part-1-start-windows-autopilot-deployment"></a>1 부: 시작 Windows 작업을 자동화할 배포
[Windows 작업을 자동화할 개요](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) 참조 하십시오.

1. 소개 하 고 Windows 작업을 자동화할 배포를 위한 필수 구성 요소를 완료 합니다. 필수 구성 요소는 다음과 같은 종류가 있습니다.
    - **장치 등록 및 OOBE 사용자 지정**

        장치를 등록 하려면 하드웨어 ID를 취득 하 고 등록 해야 합니다. 적극적으로 사용 하는 다양 한 하드웨어 공급 업체, 필요한 정보를 제공 또는 사용자를 대신 하 여 업로드할 수 있도록 합니다. 장치의 하드웨어 id.csv 파일을 생성 하는 PowerShell 스크립트를 사용 하 여 직접 하 여이 정보를 캡처하려면 옵션도 있습니다.

        장치 등록 된 후에 다음과 같은 개인 설정 및 EULA 건너뛰기를 포함 하 여 구성할 수 있는 OOBE 사용자 지정 옵션.

    - **OOBE에 대한 회사 브랜딩**

        이 옵션을 사용 하면 장치 OOBE 중에 나타날에 브랜딩 추가 수 있습니다.

    - **Microsoft Intune에서 MDM 자동 등록**
        
        자동 등록이 Azure AD를 통해 장치를 연결할 때 장치 관리에 대 한 Intune에서 자신의 Windows 10 장치를 등록할 수 있도록 합니다. 를 등록 하려면 사용자가 자신의 작업 계정을 통해 개인적으로 소유 하 고 장치를 추가 또는 Azure AD를 회사 소유의 장치에 가입 시킵니다. 백그라운드에서 장치는 또한 Intune 사용한 관리에 대 한 등록 됩니다.

    - **Windows Autopilot에서 사용되는 클라우드 서비스에 대한 네트워크 연결**

        Windows 작업을 자동화할 배포 프로그램 다양 한 클라우드 서비스를 사용 하 여 생산성을 상태로 장치를 가져올 하 고 이러한 서비스는 Windows 작업을 자동화할 장치로 등록 하는 장치에서 액세스할 수 있어야 합니다. 

    - **장치에는 Windows 10, 버전 1703 이상이 미리 설치되어 있어야 합니다.**

2. 소개 하 고 조직에 대 한 Windows 작업을 자동화할 배포 프로그램을 선택 합니다. 이러한 배포 프로그램에서 선택할 수 있습니다.
    - **비즈니스용 Microsoft Store**
    - **Microsoft Intune**
    - **파트너 센터**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Microsoft 365에 대 한 Windows 10 장치를 2 부: 설정
Microsoft 365 사용자에 대 한 Windows 장치를 설정할 수 있습니다, 전에 Windows 10, 버전 1703 (작성자 업데이트)를 실행 하는 모든 Windows 장치가 있는지 확인 이상입니다.

조직에서 모든 Windows 장치 Windows 10 작성자 업데이트를 업그레이드 하거나 않은 또는 이미 Windows 10 작성자 Update가 실행 되 고, 후 이러한 장치를 조직의 Azure Active Directory에 참가할 수 있습니다.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>새로운 또는 새로 업그레이드 Windows 10 장치 설정
Windows 10 OOBE를 사용 하 여 Windows 10 작성자 업데이트를 실행 하는 새로운 장치에서 장치를 설정 하려면 다음이 단계를 수행 (또는 이상) 또는 Windows 10 작성자 Update로 업그레이드 (또는 이상) 되었지만 즉시의 설치 프로그램을 통해 모음은 되지 않은 장치에서 합니다.

1. 구성 된 무선 네트워크를 설치 하지 않은 경우 유선을 통해 인터넷 또는 이더넷 연결에는 장치를 연결 되어있는지 확인 합니다.
2. Windows 장치 설치 경험을 통해 이동 합니다. 새롭게 제공 되거나 다시 장치에 설치 환경으로 시작 하는 **보겠습니다 시작 지역과. 이 적합?** 화면입니다.
3. 나타날 때까지 Windows 10 장치 설치 프로그램을 통해 이동은 **를 설정 하 시겠습니까?** 페이지입니다. 여기에 **조직에 대 한 설정**을 선택 합니다.
4. Microsoft 365 사용자의 계정 및 암호를 사용 하 여 로그인 합니다. 사용자 암호 설정에 따라 암호를 업데이트 하 라는 메시지가 표시 될 수 있습니다. 
5. Windows 10 장치 설정을 완료합니다.

조직의 Azure에는 장치를 연결가 끝난 후 AD 합니다.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>이미 즉시의 설치를 완료 하는 장치 설정
장치에 Windows 10 작성자 업데이트 하는 경우 (또는 이상)가 하 고 즉시의 설치 프로그램을 통해 이미으 면 다음이 단계를 수행 합니다.

1. Windows 10, 버전 1703 (작성자 업데이트)를 실행 하는 사용자의 Windows PC에서 **Windows** 로고를 선택 하 고 **설정** 아이콘을 선택 합니다.
2. **설정**에서 **계정**으로 이동합니다.
3. **사용자 정보** 페이지에서 **액세스 작업 또는 학교**선택 > **연결**합니다.
4. **대체 동작**아래에서 **작업이 나 교육용 계정 설정** 대화 상자에서 **Azure Active Directory에이 장치에 참가**선택 합니다.
5. **하기에 로그인 하면** 페이지에서 작업 시간을 입력 하거나 계정, 학교 하 고 **** 을 선택 합니다.
6. **암호 입력** 페이지에서 암호를 입력 하 고 **로그인**을 선택 합니다.
7. **이 조직 확인** 페이지에서 정보 올바르고 선택 **조인**인지를 확인 합니다.
8. **모두 설정 하 고 있는!** 페이지에서 **작업 수행**을 선택 합니다.

조직의 Azure에는 사용자가 연결 하면가 끝난 후에 AD 합니다.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>장치가 Azure AD에 연결되었는지 확인
Azure AD와 장치의 동기화 상태를 확인 하려면 다음이 단계를 수행 하 고 Microsoft 365 계정을 사용 하 여 장치를 시작 합니다. 

1. **설정**을 엽니다.
2. **Access 작업 또는 학교** 페이지 선택은 **에 연결 된 <organization name> ** **정보** 및 **연결 해제**단추를 노출 하는 영역입니다.
3. 동기화 상태를 가져오려면 **정보** 선택 합니다.
4. **동기화 상태** 페이지에서 가져올 최신 모바일 장치 관리 정책 PC에 **동기화** 선택 합니다.
5. Microsoft 365 계정을 사용 하 여를 시작 하려면 Windows **시작** 단추를 이동한 현재 계정 그림을 마우스 오른쪽 단추로 클릭 한 다음 **스위치** 는 계정을 선택 합니다.
6. 조직 전자 메일 및 암호를 사용하여 로그인합니다.

엔터프라이즈 환경에서 Windows 10을 사용 하는 경우 문제를 발생 하면 [가장 일반적인 문제에 대 한 주요 Microsoft 기술 지원 서비스 솔루션](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)을 참조할 수 있습니다. 이러한 리소스 KB 문서, 업데이트 및 라이브러리 문서에 포함 합니다.

중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step3)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [장치 상태 모니터링 및 규정 준수](windows10-enable-windows-analytics.md) |



<!--
## Phase 1: Consideration phase
This guide makes several assumptions regarding essential, business-critical considerations before upgrading an OS in an enterprise environment.

**Requirements**

Make sure you have the following requirements deployed and licensed.

| Product | License |
|:---|:---|
| Microsoft Intune | E3, E5, or Intune standalone |
| Azure AD Premium | E3 or E5 |
| Office 365 ProPlus | Business Premium, E3, E5, or Office 365 ProPlus standalone |

Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process. 

For Windows Autopilot, these are the infrastructure you need to take into account:

#### Group Policy
With Windows Autopilot, a device automatically joins their organization’s Azure AD group once a user signs into their organization from the device. The Group Policy policies (along with other customized settings and apps) are automatically pushed to the new device. It’s critical to understand that these policies must be properly configured within an organization before setting up Windows Autopilot profiles.

Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which need to be tested and implemented as part of a Windows 10 migration. The following resources provide examples on assessing current group policies for Windows, including Group Policy Objects in the Active Directory structure:

* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise


#### Data management
Be sure to back up user data if necessary. Because of the out-of-box experience (OOBE), user data isn't saved on a net-new computer. We recommend configuring a backup scenario as needed. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more info, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

We recommend using Windows Defender Antivirus and Windows Advanced Threat Protection (ATP). For more info, see [Enable Windows 10 Enterprise security features](windows10-enable-security-features.md)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostics data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see these resources:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. You need to create deployment groups to help minimize the effect on network bandwidth.

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage. 

To use Windows Autopilot, make sure you are ready to perform these tasks:
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [Diagnostics data](#step-4-diagnostics-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part of Windows deployment, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of Windows deployment, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements
To prepare for Windows 10 deployment through Windows Autopilot, make sure you meet these system requirements:
* Windows 10, version 1703 or later
* Intune licenses other mobile device management (MDM) services to manage devices
* Storage and bandwith requires minimal customization
* Diagnostic data (set at Basic level or above) - For more info, see [2.4 Diagnostic data](#24-diagnostic-data).
* Windows 10 Enterprise E3 or E5
* Devices must be registered to your organization - For more info, see [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
* Devices must be pre-installed with Windows 10, version 1703 or later
* Devices must have access to the Internet
* Azure AD Premium P1 or P2 is installed and configured and [automatic enrollment must be configured](https://go.microsoft.com/fwlink/?linkid=860700)

### Step 4: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in you organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. For more info, see:

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windowsdiagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:

1. Enable auto-enrollment using Azure AD Premium.

    To allow this functionality, see [Enable Windows 10 automatic enrollment](https://go.microsoft.com/fwlink/?linkid=860990).

2. Register device ID.

    To register devices, you need to acquire their hardware IDs. Currently, we are working with hardware vendors to enable them to provide hardware IDs or upload them on their customer’s behalf.

    Currently, Surface supports Autopilot. Autopilot support from other hardware manufacturers are upcoming. 

    To capture the hardware ID information manually, use the Get-WindowsAutopilotInfo PowerShell script. The script generates a CSV file with the device's hardware ID. Install the PowerShellGet module, download the PowerShell script, run it, save the CSV file, and then upload it to the Microsoft Store for Business.

    For more info, see:
    * [Overview of registering devices to your organization](https://go.microsoft.com/fwlink/?linkid=860991)
    * [Install and upgrade PowerShellGet module](https://go.microsoft.com/fwlink/?linkid=861001)
    * [Use PowerShell to get the device hardware ID](https://go.microsoft.com/fwlink/?linkid=861007)

    By uploading this information to the [Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=691471) or Partner Center admin portal, you'll be able to assign devices to your organization. These portals also provide additional options and customizations to configure your devices.

3. Deploy Office 365 ProPlus 2016 apps to Windows 10 devices using Intune.

    For a Microsoft 365 powered device, you'll need to deploy the Office 365 ProPlus 2016 suite to Windows 10 user groups. To do this:
    1. Configure the app suite by choosing specific Office 365 ProPlus apps.
    2. Configure app information, such as suite name, description, and category.
    3. Configure app settings, including versioning (32-bit versus 64-bit), the update channel, and languages.
    4. Save these configurations.

    The app suite should show up in the app panel. If you see an error message, see [Assign Office 365 ProPlus apps to devices that run Windows 10](https://go.microsoft.com/fwlink/?linkid=857153) to help troubleshoot the issue.

4. Deploy Windows Autopilot.

    You can manage devices for your organization and apply an Autopilot deployment profile to your devices. When people in your organization run the OOBE for the device, the profile configures Windows based on the Autopilot deployment profile you applied to the device. As part of the overall process, you need to perform these tasks:
    1. Add devices
    2. Group devices (optional)
    3. Create Autopilot deployment profile
    4. Apply Autopilot deployment profile

    For step-by-step guidance see [Manage Windows device deployment with Windows Autopilot](https://go.microsoft.com/fwlink/?linkid=852442).

    For end users, they can set up a device that's been configured through Autopilot by:
    1. Turning on the new Windows 10 device.
    2. Selecting the language.
    3. Connecting to a network.
    4. Entering their Azure AD email and password.

    Azure AD Join and MDM then automatically enroll the device. MDM also applies organization-configured policies, settings, and apps.

5. Manage Windows device deployment with Windows Autopilot deployment.

    You can manage new devices in the [Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=691471). New devices must meet these requirements:
    * Have Windows 10, version 1703 or later installed
    * Have not been through Windows OOBE

    For more info, see [Manage Autopilot deployment profiles using Microsoft Store for Business](https://go.microsoft.com/fwlink/?linkid=852441).

-->


