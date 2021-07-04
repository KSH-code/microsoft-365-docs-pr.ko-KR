---
title: PowerShell을 통해 비즈니스용 Skype Oline 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Microsoft 365용 PowerShell을 사용하여 비즈니스용 Skype Online 정책, 사용자별 정책 및 모임 설정을 관리할 수 있습니다.
ms.openlocfilehash: 4ea4858e4ca334cdb0268312e69bef77bc9bbd86
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288986"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="cdb18-103">PowerShell을 통해 비즈니스용 Skype Oline 관리</span><span class="sxs-lookup"><span data-stu-id="cdb18-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="cdb18-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="cdb18-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cdb18-105">비즈니스용 Skype Online 관리자는 정책 관리를 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="cdb18-106">Microsoft 365 관리 센터에서 이러한 작업 중 일부를 수행할 수 있지만 다른 작업은 PowerShell에서 보다 간편하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="cdb18-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="cdb18-107">Before you start</span></span>

> [!NOTE]
> <span data-ttu-id="cdb18-108">Skype for Business Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="cdb18-109">최신 Teams PowerShell 공개 릴리스를 사용 중인 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

<span data-ttu-id="cdb18-110">[Teams PowerShell 모듈](/microsoftteams/teams-powershell-install)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>

## <a name="connect-using-admin-credentials"></a><span data-ttu-id="cdb18-111">관리자 자격 증명을 사용하여 연결</span><span class="sxs-lookup"><span data-stu-id="cdb18-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="cdb18-112">Windows PowerShell 명령 프롬프트 창을 열고 다음의 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="cdb18-113">**Windows PowerShell 자격 증명 요청** 대화 상자에서 관리자 계정 이름과 암호를 입력한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="cdb18-114">다단계 인증과 함께 관리자 계정을 사용하여 연결</span><span class="sxs-lookup"><span data-stu-id="cdb18-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="cdb18-115">Windows PowerShell 명령 프롬프트 창을 열고 다음의 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="cdb18-116">표시될 때 비즈니스용 Skype Online 관리자 계정 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="cdb18-117">**계정에 로그인** 대화 상자에서 비즈니스용 Skype Online 관리자 암호를 입력한 다음 **로그인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="cdb18-118">**계정에 로그인** 대화 상자에서 지침에 따라 확인 코드와 같은 인증 정보를 추가한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdb18-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="cdb18-119">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdb18-119">For more information, see:</span></span>

- [<span data-ttu-id="cdb18-120">PowerShell을 사용하여 온라인 비즈니스 정책용 Skype 관리</span><span class="sxs-lookup"><span data-stu-id="cdb18-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [<span data-ttu-id="cdb18-121">Powershell 비즈니스 온라인 정책에 대 한 사용자당 Skype 할당</span><span class="sxs-lookup"><span data-stu-id="cdb18-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a><span data-ttu-id="cdb18-122">기타 참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdb18-122">See also</span></span>

[<span data-ttu-id="cdb18-123">PowerShell로 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="cdb18-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="cdb18-124">Microsoft 365용 PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="cdb18-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="cdb18-125">비즈니스용 Skype Online PowerShell cmdlet 참조자료</span><span class="sxs-lookup"><span data-stu-id="cdb18-125">Skype for Business PowerShell cmdlet references</span></span>](/powershell/module/skype/)
