---
title: Microsoft 365 비즈니스에서 관리 되는 도메인 가입 Windows 10 장치를 사용 하도록 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 보호 하기 위해 Microsoft 365를 사용 하도록 설정 하는 방법에 알아봅니다 로컬 AD Windows 10 장치에 참가 합니다.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869868"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="958b0-103">Microsoft 365 비즈니스에서 관리 되는 도메인 가입 Windows 10 장치를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="958b0-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="958b0-p101">조직에서 Windows Server Active Directory를 온-프레미스를 사용 하는 경우 로컬 인증을 요구 하는 온-프레미스 리소스에 대 한 액세스를 유지 하면서 Windows 10 장치로 보호 하기 위해 Microsoft 365 비즈니스를 설정할 수 있습니다. Azure AD를 사용한 Windows 10 장치를 등록 하 고 Microsoft 365 비즈니스 하 여 모바일 장치 관리에 대 한이 등록 앞에 오는 Azure Active Directory와 Active Directory을 동기화 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="958b0-106">Microsoft 365 비즈니스에 의해 관리를 도메인에 가입 된 장치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="958b0-p102">조직의 도메인에 가입 된 장치 온-프레미스 Active Directory 외에도 Azure Active Directory에서 제공 하는 기능을 활용할 수를 설정 하려면 **하이브리드 Azure AD 가입 장치를**구현할 수 있습니다. 이 온-프레미스 Active Directory와 Azure Active Directory에 가입 된 장치입니다. 하이브리드에 참가 하는 Azure AD 장치 보호 하 고 Microsoft 365 비즈니스에서 관리 하는 수입니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="958b0-110">하이브리드 Azure AD에 참가 하 고 Microsoft 365 비즈니스에서 관리 하는 Windows 10 장치를 확인 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="958b0-111">Azure Active Directory에 사용자, 그룹 및 로컬 Active Directory에서 연락처를 동기화 하는 디렉터리 동기화 마법사 및 Azure Active Directory 연결 [Office 365에 대 한 디렉터리 동기화 설정](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)의 설명에 따라 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="958b0-112">단계는 Microsoft 365 비즈니스용 정확 하 게 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="958b0-113">Azure AD에 참가 하는 하이브리드 되도록 Windows 10 장치를 사용 하도록 설정 하려면 3 단계를 완료 하기 전에 다음 필수 구성 요소를 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="958b0-114">Azure AD의 최신 버전을 실행 하는 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="958b0-p103">Azure AD 연결 하이브리드 Azure AD에 참가 하려는 장치에 있는 모든 컴퓨터 개체를 동기화 했습니다. 컴퓨터 개체는 특정 조직 구성 단위 (OU)에 속하는 다음 이러한 Ou Azure AD에 동기화에 대 한 설정 되었는지 확인 하는 경우도 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="958b0-117">하이브리드 Azure AD 가입 Intune (Microsoft 365 비즈니스) 하 여 모바일 장치 관리에 대 한 등록 하 고 있는 기존 도메인 가입 Windows 10 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="958b0-p104">[하이브리드 Azure Active Directory에 참가 장치를 구성 하는 방법](https://go.microsoft.com/fwlink/p/?linkid=872870)에 단계별 지침을 따릅니다. 온-프레미스 Active directory 동기화를 사용 하는이 Windows 10 컴퓨터에 참가 하 고 ready 클라우드 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="958b0-p105">모바일 장치 관리에 대 한 Windows 10 장치를 등록 하기 위해 지침에 대 한 [그룹 정책을 사용 하 여 Intune 사용한 Windows 10 장치 등록](https://go.microsoft.com/fwlink/p/?linkid=872871) 을 참조 하십시오. 나 설정할 수 있습니다는 그룹 정책 로컬 컴퓨터에서 수준 대량 작업에 대 한 도메인 컨트롤러 서버에서이 그룹 정책 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="958b0-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

