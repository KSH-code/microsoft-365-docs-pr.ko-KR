---
title: 도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365에서 로컬 AD에 가입 된 Windows 10 장치를 보호 하도록 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660341"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="a651b-103">도메인에 가입 된 Windows 10 장치를 Microsoft 365 Business에서 관리할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a651b-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="a651b-104">조직에서 Windows Server Active Directory 온-프레미스를 사용 하는 경우에는 Microsoft 365 Business를 설정 하 여 Windows 10 장치를 보호 하 되, 로컬 인증을 필요로 하는 온-프레미스 리소스에 대 한 액세스를 계속 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="a651b-105">먼저 Active Directory를 Azure Active Directory와 동기화 한 다음 Azure AD를 사용 하 여 Windows 10 장치를 등록 하 고 Microsoft 365 Business에서 모바일 장치 관리용으로 등록 하 여이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="a651b-106">Microsoft 365 Business에서 관리할 도메인 가입 장치 설정</span><span class="sxs-lookup"><span data-stu-id="a651b-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="a651b-107">온-프레미스 Active Directory 외에 Azure Active Directory에서 제공 하는 기능을 활용 하기 위해 조직의 도메인에 가입 된 장치를 설정 하려면 **하이브리드 AZURE AD에 가입 된 장치**를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="a651b-108">온-프레미스 Active Directory 및 Azure Active Directory에 모두 가입 된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="a651b-109">하이브리드 Azure 연결 된 장치는 Microsoft 365 Business에서 보호 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="a651b-110">Windows 10 장치 하이브리드 Azure AD를 가입 하 고 Microsoft 365 Business에 의해 관리 되도록 하려면 아래 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="a651b-111">사용자, 그룹 및 연락처를 로컬 Active Directory에서 Azure Active Directory로 동기화 하려면 [Set up directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에 설명 된 대로 디렉터리 동기화 마법사 및 Azure Active Directory Connect를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a651b-112">이 단계는 Microsoft 365 비즈니스에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="a651b-113">3 단계를 완료 하 여 Windows 10 장치를 하이브리드 Azure AD에 연결 된 상태로 설정 하기 전에 다음 필수 구성 요소를 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="a651b-114">최신 버전의 Azure AD connect를 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="a651b-115">Azure AD connect에서 하이브리드 Azure AD에 가입 하려는 장치의 모든 컴퓨터 개체를 동기화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="a651b-116">컴퓨터 개체가 특정 OU (조직 구성 단위)에 속하는 경우 이러한 Ou가 Azure AD connect 에서도 동기화 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="a651b-117">Intune에서 하이브리드 Azure AD에 가입 하 고 사용자가 모바일 장치 관리용으로 등록할 수 있도록 기존 도메인에 가입 된 Windows 10 장치 등록 (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="a651b-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="a651b-118">[하이브리드 Azure Active Directory 가입 된 장치를 구성 하는 방법](https://go.microsoft.com/fwlink/p/?linkid=872870)에 대 한 단계별 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="a651b-119">이렇게 하면 온-프레미스 Active Directory에 가입 된 Windows 10 컴퓨터를 동기화 하 고 클라우드를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="a651b-120">Windows 10 장치를 모바일 장치 관리에 등록 하려면 설명을 위해 [그룹 정책을 사용 하 여 Intune을 사용 하 여 windows 10 장치 등록](https://go.microsoft.com/fwlink/p/?linkid=872871) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a651b-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="a651b-121">로컬 컴퓨터 수준에서 또는 대량 작업을 위해 그룹 정책을 설정할 수 있으며, 도메인 컨트롤러 서버에서이 그룹 정책 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a651b-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>