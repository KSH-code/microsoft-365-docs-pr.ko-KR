---
title: Office 365 메시지 암호화 관리
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: OME(Office 365 메시지 암호화 설정)를 완료한 후 여러 가지 방법으로 배포를 사용자 지정하는 방법을 설명합니다.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650987"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="0b2e9-103">Office 365 메시지 암호화 관리</span><span class="sxs-lookup"><span data-stu-id="0b2e9-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="0b2e9-104">OME(Office 365 메시지 암호화 설정한 후 여러 가지 방법으로 배포 구성을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="0b2e9-105">예를 들어 일회용 암호를 사용하도록 설정할지 여부를 구성하고, 웹의 코드에 암호화 단추를 Outlook 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="0b2e9-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="0b2e9-106">이 문서의 작업에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="0b2e9-107">Google, Yahoo 및 Microsoft 계정 받는 사람이 이러한 계정을 사용하여 앱 포털에 로그인할 Office 365 메시지 암호화 관리</span><span class="sxs-lookup"><span data-stu-id="0b2e9-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="0b2e9-108">새 Office 365 메시지 암호화 기능을 설정하면 조직의 사용자가 조직 외부의 받는 사람에게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="0b2e9-109">받는 사람이 Google 계정, Yahoo 계정 또는 Microsoft 계정과 같은 소셜 *ID를* 사용하는 경우 받는 사람은 소셜 ID를 사용하여 OME 포털에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="0b2e9-110">원하는 경우 받는 사람이 공유 ID를 사용하여 OME 포털에 로그인하도록 허용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="0b2e9-111">받는 사람이 소셜 ID를 사용하여 OME 포털에 로그인할 수 있는지 여부를 관리하기 위해</span><span class="sxs-lookup"><span data-stu-id="0b2e9-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="0b2e9-112">[커넥트 PowerShell을 Exchange Online 를 사용할 수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0b2e9-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-113">다음과 Set-OMEConfiguration SocialIdSignIn 매개 변수를 사용하여 Set-OMEConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="0b2e9-114">예를 들어 공유 ID를 사용하지 않도록 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0b2e9-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="0b2e9-115">공유 ID를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="0b2e9-116">사이트 포털에 일회용 패스 코드 사용 Office 365 메시지 암호화 관리</span><span class="sxs-lookup"><span data-stu-id="0b2e9-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="0b2e9-117">OME로 암호화된 메시지의 받는 사람이 받는 사람이 Outlook 사용하는 계정에 관계없이 받는 사람은 메시지를 읽을 수 있는 제한된 시간의 웹 보기 링크를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="0b2e9-118">이 링크에는 일회용 패스 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="0b2e9-119">관리자는 받는 사람이 일회용 패스 코드를 사용하여 OME 포털에 로그인할 수 있는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="0b2e9-120">OME에서 일회성 통과 코드를 생성하는지 여부를 관리하기 위해</span><span class="sxs-lookup"><span data-stu-id="0b2e9-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="0b2e9-121">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-122">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-123">OTPEnabled Set-OMEConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="0b2e9-124">예를 들어 일회성 통과 코드를 사용하지 않도록 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0b2e9-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="0b2e9-125">일회성 통과 코드를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="0b2e9-126">웹에서 암호화 단추의 Outlook 관리</span><span class="sxs-lookup"><span data-stu-id="0b2e9-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="0b2e9-127">관리자는 최종 사용자에게 이 단추를 표시할지 여부를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="0b2e9-128">웹에서 암호화 단추가 Outlook 여부를 관리하기 위해</span><span class="sxs-lookup"><span data-stu-id="0b2e9-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="0b2e9-129">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-130">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-131">-Set-IRMConfiguration -SimplifiedClientAccessEnabled 매개 변수를 사용하여 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="0b2e9-132">예를 들어 암호화 단추를 **사용하지 않도록 설정하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="0b2e9-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="0b2e9-133">암호화 **단추를 사용하도록** 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="0b2e9-134">iOS 메일 앱 사용자에 대해 전자 메일 메시지의 서비스 쪽 암호 해독 사용</span><span class="sxs-lookup"><span data-stu-id="0b2e9-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="0b2e9-135">iOS 메일 앱은 365로 보호된 메시지의 암호를 해독할 Office 365 메시지 암호화.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="0b2e9-136">관리자로서 Microsoft 365 iOS 메일 앱으로 배달된 메시지에 대해 서비스 쪽 암호 해독을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="0b2e9-137">서비스 쪽 암호 해독을 사용하기로 선택하면 서비스에서 암호 해독된 메시지 복사본을 iOS 장치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="0b2e9-138">클라이언트 장치는 암호 해독된 메시지 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="0b2e9-139">또한 이 메시지는 iOS 메일 앱이 사용자에게 클라이언트 쪽 사용 권한을 적용하지 않는 경우에도 사용 권한에 대한 정보를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="0b2e9-140">사용자가 원래 메시지를 복사하거나 인쇄할 수 있는 권한은 없는 경우에도 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="0b2e9-141">그러나 사용자가 메시지 전달과 같은 Microsoft 365 메일 서버가 필요한 작업을 완료하려고 하면 원래 사용자에게 사용권이 없는 경우 서버에서 해당 작업을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="0b2e9-142">그러나 최종 사용자는 iOS 메일 앱 내의 다른 계정에서 메시지를 전달하여 "전달 금지" 사용 제한을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="0b2e9-143">메일의 서비스 쪽 암호 해독을 설정하는지 여부에 관계없이 암호화된 메일 및 권한으로 보호된 메일에 대한 첨부 파일은 iOS 메일 앱에서 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="0b2e9-144">암호 해독된 메시지를 iOS 메일 앱 사용자에게 보낼 수 있도록 허용하지 않는 경우 사용자는 메시지를 볼 수 있는 권한을 받지 못했다는 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="0b2e9-145">기본적으로 전자 메일 메시지의 서비스 쪽 암호 해독은 사용하도록 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="0b2e9-146">자세한 내용은 클라이언트 환경의 보기를 참조하세요. iPhone 또는 [iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="0b2e9-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="0b2e9-147">iOS 메일 앱 사용자가 iOS 메일 앱으로 보호된 메시지를 볼 수 Office 365 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="0b2e9-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="0b2e9-148">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-149">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-150">AllowRMSSupportForUnenlightenedApps 매개 Set-ActiveSyncOrganizations cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="0b2e9-151">예를 들어 iOS 메일 앱과 같은 비인식 앱으로 메시지를 보내기 전에 메시지를 암호 해독하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="0b2e9-152">또는 암호 해독된 메시지를 비인도 앱으로 보내지 못하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="0b2e9-153">개별 사서함 정책(OWA/ActiveSync)은 이러한 설정(예: 각 OWA 사서함 정책 또는 ActiveSync 사서함 정책 내에서 -IRMEnabled를 False로 설정한 경우) 이러한 구성이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="0b2e9-154">웹 브라우저 메일 클라이언트에 대해 전자 메일 첨부 파일 서비스 쪽 암호 해독 사용</span><span class="sxs-lookup"><span data-stu-id="0b2e9-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="0b2e9-155">일반적으로 메시지 암호화를 Office 365 첨부 파일이 자동으로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="0b2e9-156">관리자는 사용자가 웹 브라우저에서 다운로드하는 전자 메일 첨부 파일에 대해 서비스 쪽 암호 해독을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="0b2e9-157">서비스 쪽 암호 해독을 사용하면 서비스에서 암호 해독된 파일의 복사본을 장치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="0b2e9-158">메시지가 계속 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-158">The message is still encrypted.</span></span> <span data-ttu-id="0b2e9-159">또한 전자 메일 첨부 파일은 브라우저가 사용자에게 클라이언트 쪽 사용 권한을 적용하지 않는 경우에도 사용 권한에 대한 정보를 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="0b2e9-160">사용자는 원래 전자 메일 첨부 파일을 복사하거나 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="0b2e9-161">그러나 사용자가 첨부 파일 전달과 같은 Microsoft 365 메일 서버가 필요한 작업을 완료할 경우 원래 사용자에게 사용권이 없는 경우 서버에서 해당 작업을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="0b2e9-162">첨부 파일에 대한 서비스 쪽 암호 해독을 설정하는지 여부에 관계없이 사용자는 iOS 메일 앱에서 암호화되고 권한으로 보호된 메일에 대한 첨부 파일을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="0b2e9-163">암호 해독된 전자 메일 첨부 파일(기본값)을 허용하지 않는 경우 사용자는 첨부 파일을 볼 수 있는 권한을 받지 못했다는 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="0b2e9-164">전자 메일 및 전자 Microsoft 365 암호화를 구현하는 방법에 대한 자세한 내용은 Encrypt-Only 전자 메일에 대한 암호화 [전용 옵션을 참조하세요.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="0b2e9-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="0b2e9-165">웹 브라우저에서 다운로드 시 전자 메일 첨부 파일을 암호 해독할지 여부를 관리하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="0b2e9-166">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-167">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-168">DecryptAttachmentForEncryptOnly 매개 Set-IRMConfiguration 사용하여 Set-IRMConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="0b2e9-169">예를 들어 사용자가 웹 브라우저에서 전자 메일 첨부 파일을 다운로드할 때 암호를 해독하도록 서비스를 구성하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="0b2e9-170">암호화된 전자 메일 첨부 파일을 다운로드 시 그대로 두도록 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="0b2e9-171">모든 외부 받는 사람이 OME 포털을 사용하여 암호화된 메일을 읽는지 확인</span><span class="sxs-lookup"><span data-stu-id="0b2e9-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="0b2e9-172">사용자 지정 브랜드 템플릿을 사용하여 받는 사람이 웹에서 또는 웹에서 Outlook 대신 OME 포털에서 암호화된 전자 메일을 읽게 하는 래퍼 Outlook 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="0b2e9-173">받는 사람이 받는 메일을 사용하는 방법을 보다 잘 제어하려는 경우 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="0b2e9-174">예를 들어 외부 받는 사람이 웹 포털에서 전자 메일을 보는 경우 전자 메일의 만료 날짜를 설정하고 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="0b2e9-175">이러한 기능은 OME 포털을 통해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="0b2e9-176">메일 흐름 규칙을 만들 때 암호화 옵션과 전달 금지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="0b2e9-177">사용자 지정 템플릿을 사용하여 모든 외부 받는 사람이 OME 포털 및 암호화된 전자 메일을 강제로 사용</span><span class="sxs-lookup"><span data-stu-id="0b2e9-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="0b2e9-178">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-179">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-180">다음 New-TransportRule 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="0b2e9-181">여기서 각 부분이 나타내는 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-181">where:</span></span>

   - <span data-ttu-id="0b2e9-182">`mail flow rule name` 은 새 메일 흐름 규칙에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="0b2e9-183">`option name` 는 `Encrypt` 또는 `Do Not Forward` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="0b2e9-184">`template name` 은 사용자 지정 브랜징 템플릿에 지정한 이름(예: `OME Configuration` )입니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="0b2e9-185">"OME 구성" 템플릿을 사용하여 모든 외부 전자 메일을 암호화하고 다음 Encrypt-Only 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="0b2e9-186">"OME 구성" 템플릿을 사용하여 모든 외부 전자 메일을 암호화하고 전달하지 않습니다 옵션을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="0b2e9-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="0b2e9-187">전자 메일 메시지 및 OME 포털의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0b2e9-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="0b2e9-188">조직에 맞게 OME를 사용자 지정하는 방법에 대한 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="0b2e9-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="0b2e9-189">OME에 대한 새 기능을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0b2e9-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="0b2e9-190">이 기능이 필요하지는 않지만 필요한 경우 OME에 대한 새 기능을 사용할 수 없는 것은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="0b2e9-191">먼저 새 OME 기능을 사용하는 메일 흐름 규칙을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="0b2e9-192">메일 흐름 규칙을 제거하는 데 대한 자세한 내용은 메일 흐름 [규칙 관리를 참조하십시오.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="0b2e9-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="0b2e9-193">그런 다음 PowerShell에서 Exchange Online 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="0b2e9-194">OME에 대한 새 기능을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="0b2e9-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="0b2e9-195">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="0b2e9-196">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b2e9-197">웹용 웹  Outlook 암호화 단추를 사용하도록 설정한 경우 SimplifiedClientAccessEnabled 매개 Set-IRMConfiguration cmdlet을 실행하여 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="0b2e9-198">그렇지 않은 경우 이 단계를 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="0b2e9-199">AzureRMSLicensingEnabled 매개 변수를 false로 Set-IRMConfiguration cmdlet을 실행하여 OME에 대한 새 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b2e9-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
