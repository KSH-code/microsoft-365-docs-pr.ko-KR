---
title: 사용자 지정 도메인에서 전자 메일에 DKIM을 사용하는 방법
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365에서 DKIM(도메인키 식별 메일)을 사용하여 사용자 지정 도메인에서 보낸 메시지를 대상 전자 메일 시스템에서 신뢰하는지 확인하는 방법을 알아봅니다.
ms.openlocfilehash: 0c77798f0bf4b5dedfa5023eaa0b4de4ab8c5b64
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871000"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="a8505-103">DKIM을 사용하여 사용자 지정 도메인에서 전송한 아웃바운드 전자 메일의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a8505-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="a8505-104">**요약:** 이 문서에서는 대상 전자 메일 시스템에서 사용자 지정 도메인에서 보낸 메시지를 신뢰하는지 확인하기 위해 Office 365에서 DomainKeys 식별 메일 (DKIM)을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="a8505-105">SPF 및 DMARC와 함께 DKIM을 사용하여 spoofer로 하여금 사용자의 도메인에서 오는 것처럼 보이는 메시지를 보내지 못하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="a8505-106">DKIM을 사용하면 보내는 전자 메일 메시지의 머리글에 디지털 서명을 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="a8505-107">복잡해 보이지만 실제로는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="a8505-108">DKIM을 구성할 때 암호화 인증을 사용하여 전자 메일 메시지에 해당 이름을 연결하거나 서명할 수 있는 권한을 도메인에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="a8505-109">사용자의 도메인으로부터 전자 메일을 수신하는 전자 메일 시스템에서는 이 디지털 서명을 사용하여 수신하는 전자 메일이 합법적인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="a8505-110">기본적으로 개인 키를 사용하여 사용자의 도메인의 보내는 전자 메일에서 머리글을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="a8505-111">사용자의 DNS 레코드에 공개 키를 게시하면 수신하는 서버에서 이를 이용하여 서명을 디코딩하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="a8505-112">공개 키를 사용하여 메시지가 실제로 사용자로부터 온 것이고 도메인을 *스푸핑한* 사람에게서 온 것이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="a8505-113">Microsoft 365는 초기 'onmicrosoft.com' 도메인에 대해 DKIM을 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="a8505-114">즉, 초기 도메인 이름(예: litware.onmicrosoft.com)의 DKIM을 설정하기 위한 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="a8505-115">도메인에 대한 자세한 내용은 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="a8505-116">사용자 지정 도메인의 DKIM에 대해서 아무 것도 수행하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="a8505-117">사용자 지정 도메인에 DKIM을 설정하지 않으면 Microsoft 365는 개인 및 공개 키 쌍을 만들고 DKIM 서명을 사용하도록 설정 한 다음 사용자 지정 도메인에 대한 Microsoft 365 기본 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="a8505-118">대부분의 Microsoft 365 고객에게는 이 기능으로 충분하지만 다음과 같은 경우에는 사용자 지정 도메인에 대해 DKIM을 수동으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="a8505-119">Microsoft 365에 두 개 이상의 사용자 지정 도메인이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="a8505-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="a8505-120">DMARC 또한 설정하려는 경우 (권장됨)</span><span class="sxs-lookup"><span data-stu-id="a8505-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="a8505-121">개인 키를 제어하려는 경우</span><span class="sxs-lookup"><span data-stu-id="a8505-121">You want control over your private key</span></span>

- <span data-ttu-id="a8505-122">CNAME 레코드를 사용자 지정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="a8505-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="a8505-123">타사 대량 메일 프로그램을 사용하는 경우와 같이 타사 도메인에서 시작되는 전자 메일에 대해 DKIM 키를 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="a8505-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="a8505-124">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="a8505-124">In this article:</span></span>

- [<span data-ttu-id="a8505-125">악의적인 스푸핑을 방지하기 위해 DKIM이 SPF 단독보다 더욱 효율적인 방식인 이유</span><span class="sxs-lookup"><span data-stu-id="a8505-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="a8505-126">수동으로 1024 비트 키를 2048 비트 DKIM 암호화 키로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="a8505-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="a8505-127">DKIM을 수동으로 설정하는 데 필요한 단계</span><span class="sxs-lookup"><span data-stu-id="a8505-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="a8505-128">두 개 이상의 사용자 지정 도메인에 대해 DKIM을 구성</span><span class="sxs-lookup"><span data-stu-id="a8505-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="a8505-129">사용자 지정 도메인에 대해 DKIM 서명 정책을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8505-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="a8505-130">DKIM 및 Microsoft 365의 기본 동작</span><span class="sxs-lookup"><span data-stu-id="a8505-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="a8505-131">타사 서비스에서 사용자 지정 도메인을 대신하여 이메일을 보내거나 스푸핑할 수 있도록 DKIM을 설정</span><span class="sxs-lookup"><span data-stu-id="a8505-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="a8505-132">다음 단계: Microsoft 365에 대한 DKIM을 설정한 후</span><span class="sxs-lookup"><span data-stu-id="a8505-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="a8505-133">악의적인 스푸핑을 방지하기 위해 DKIM이 SPF 단독보다 더욱 효율적인 방식인 이유</span><span class="sxs-lookup"><span data-stu-id="a8505-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="a8505-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="a8505-135">SPF는 메시지 봉투에 정보를 추가하지만 DKIM은 실제로 메시지 머리글 내에서 서명을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="a8505-136">메시지를 전달할 때 메시지의 봉투 일부가 전달 서버에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="a8505-137">디지털 서명은 전자 메일 머리글의 일부이기 때문에 전자 메일 메시지와 함께 유지되므로 DKIM은 다음 예제와 같이 메시지가 전달된 경우에도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![SPF 확인이 실패하는 경우 DKIM 인증을 제공하는 전달된 메시지를 보여주는 다이어그램](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="a8505-139">이 예제에서 도메인에 대한 SPF TXT 레코드만 게시한 경우 받는 사람의 메일 서버에서 전자 메일을 스팸으로 표시하고 가양성 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="a8505-140">이 시나리오에 DKIM을 추가하면 가양성 스팸 보고를 줄일 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="a8505-141">DKIM은 IP 주소뿐만 아니라 인증을 위해 공개 키 암호화를 사용하기 때문에 DKIM은 SPF보다 훨씬 강력한 인증 형식으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="a8505-142">배포시 SPF 및 DKIM과 DMARC를 모두 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="a8505-143">핵심: DKIM은 개인 키를 사용하여 암호화 된 서명을 메시지 머리글에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="a8505-144">서명 도메인 또는 아웃 바운드 도메인이 머리글의 **d =** 필드 값으로 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="a8505-145">확인 도메인 또는 수신자 도메인은 **d =** 필드를 사용하여 DNS에서 공개 키를 조회하고 메시지를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="a8505-146">메시지를 확인하면 DKIM 검사가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-146">If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="a8505-147">수동으로 1024 비트 키를 2048 비트 DKIM 암호화 키로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="a8505-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="a8505-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="a8505-149">1024 및 2048 비트가 모두 DKIM 키에 대한 지원 을 받게되므로 다음의 지침은 1024 비트 키를 2048로 업그레이드하는 방법을 설명할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="a8505-150">다음은 두 가지 사용 사례에 대한 단계입니다. 구성에 가장 적합한 한 사례를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="a8505-151">**이미 DKIM을 구성한 경우** 다음과 같이 비트를 회전시킵니다:</span><span class="sxs-lookup"><span data-stu-id="a8505-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="a8505-152">[PowerShell을 통해 Office 365 작업 부하에 연결합니다](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="a8505-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="a8505-153">(Cmdlet은 Exchange Online에서 제공됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a8505-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="a8505-154">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-154">Run the following command:</span></span>

      ```powershell
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="a8505-155">또는 **DKIM의 새로운 구현의 경우**:</span><span class="sxs-lookup"><span data-stu-id="a8505-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="a8505-156">[PowerShell을 통해 Office 365 작업 부하에 연결합니다](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="a8505-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="a8505-157">(이는 Exchange Online cmdlet입니다.)</span><span class="sxs-lookup"><span data-stu-id="a8505-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="a8505-158">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="a8505-159">Microsoft 365로의 연결 상태를 유지하여 구성을 *검증* 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="a8505-160">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="a8505-161">이 새 2048 비트 키는 RotateOnDate에 적용되며그 사이에 1024 비트 키로 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="a8505-162">4 일 후 2048 비트 키 (즉, 두 번째 선택기에 회전이 적용되는 경우)를 사용하여 다시 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="a8505-163">두 번째 선택기를 회전하려면 a) Microsoft 365 서비스가 선택기를 회전시키게 하고 6개월 이내에 2048 비트로 업그레이드하거나 b) 4일 후 2048 비트가 사용되고 있는지 확인한 후 나열된 적절 한 cmdlet을 사용하여 수동으로 두 번째 회전기 키를 회전시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="a8505-164">DKIM을 수동으로 설정하는 데 필요한 단계</span><span class="sxs-lookup"><span data-stu-id="a8505-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="a8505-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="a8505-166">DKIM을 구성하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="a8505-167">DNS에서 사용자 지정 도메인에 대해 두 개의 CNAME 레코드 게시</span><span class="sxs-lookup"><span data-stu-id="a8505-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="a8505-168">사용자 지정 도메인에 DKIM 서명 사용</span><span class="sxs-lookup"><span data-stu-id="a8505-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="a8505-169">DNS에서 사용자 지정 도메인에 대해 두 개의 CNAME 레코드 게시</span><span class="sxs-lookup"><span data-stu-id="a8505-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="a8505-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="a8505-171">DNS에 DKIM 서명을 추가하려는 각 도메인에 대해 두 개의 CNAME 레코드를 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="a8505-172">전체 기사를 읽지 않은 경우 시간을 절약하는 다음과 같은 PowerShell 연결 정보를 놓쳤을 수 있습니다. [PowerShell을 통해 Office 365 워크로드](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-172">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="a8505-173">(Cmdlet은 Exchange Online에서 제공됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a8505-173">(The cmdlet comes from Exchange Online.)</span></span>

<span data-ttu-id="a8505-174">다음 명령을 실행하여 선택기 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-174">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="a8505-175">Microsoft 365의 초기 도메인 외에 사용자 지정 도메인을 프로비저닝한 경우에는 추가 도메인마다 두 개의 CNAME 레코드를 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-175">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="a8505-176">따라서 두 개의 도메인이 있는 경우 두 개의 CNAME 레코드를 모두 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-176">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="a8505-177">CNAME 레코드에는 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-177">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8505-178">사용자가 GCC High 고객인 경우 _domainGuid_ 를 다르게 계산합니다!</span><span class="sxs-lookup"><span data-stu-id="a8505-178">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="a8505-179">_domainGuid_ 를 계산하기 위해 _initialDomain_ 에 대한 MX 레코드를 조회하는 대신 사용자 정의된 도메인에서 직접 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-179">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="a8505-180">예를 들어, 사용자 지정 도메인이 "contoso.com"인 경우 domainGuid는 "contoso-com"이되고 마침표는 대시로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-180">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="a8505-181">따라서 initialDomain이 가리키는 MX 레코드와 상관없이 항상 위의 방법을 사용하여 CNAME 레코드에서 사용할 domainGuid를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-181">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="a8505-182">여기서,</span><span class="sxs-lookup"><span data-stu-id="a8505-182">Where:</span></span>

- <span data-ttu-id="a8505-183">Microsoft 365의 경우 셀렉터는 항상 "selector1" 또는 "selector2"입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-183">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="a8505-184">_domainGUID_ 는 mail.protection.outlook.com 이전에 표시되는 사용자 정의 도메인에 대한 사용자 정의된 MX 레코드의 _domainGUID_ 와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-184">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="a8505-185">예를 들어 도메인 contoso.com에 대한 다음 MX 레코드에서 _domainGUID_ 는 contoso-com입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-185">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="a8505-186">@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a8505-186">contoso.com.</span></span>  <span data-ttu-id="a8505-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a8505-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="a8505-188">_initialdomain_ 은 Microsoft 365에 등록할 때 사용한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-188">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="a8505-189">초기 도메인은 항상 onmicrosoft.com으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-189">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="a8505-190">초기 도메인을 확인하는 방법에 대한 자세한 내용은 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-190">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="a8505-191">예를 들어 cohovineyardandwinery.onmicrosoft.com이라는 초기 도메인과 cohovineyard.com 및 cohowinery.com이라는 두 개의 사용자 지정 도메인이 있는 경우 추가 도메인마다 총 두 개의 CNAME 레코드를 설정해야 합니다 (총 네 개의 CNAME 레코드).</span><span class="sxs-lookup"><span data-stu-id="a8505-191">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="a8505-192">두 번째 레코드를 만드는 것도 중요하지만, 생성 시 선택 도구 중 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-192">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="a8505-193">본질적으로, 두 번째 선택기는 아직 생성되지 않은 주소를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-193">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="a8505-194">키 회전이 원활하게 진행되므로 두 번째 CNAME 레코드를 만드는 것을 당사는 계속 권장했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-194">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="a8505-195">사용자 지정 도메인에 DKIM 서명 사용</span><span class="sxs-lookup"><span data-stu-id="a8505-195">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="a8505-196"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-196"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="a8505-197">CNAME 레코드를 DNS에 게시하면 Microsoft 365를 통해 DKIM 서명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-197">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="a8505-198">Microsoft 365 관리 센터 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-198">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="a8505-199">관리 센터를 통해 사용자 지정 도메인에 DKIM 서명 사용</span><span class="sxs-lookup"><span data-stu-id="a8505-199">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="a8505-200">회사 또는 학교 계정으로 [Microsoft 365에 로그인](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-200">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="a8505-201">왼쪽 위에서 앱 시작 관리자 아이콘을 선택하고 **관리자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-201">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="a8505-202">왼쪽 아래 탐색에서 **관리자** 를 확장하고 **Exchange** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-202">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="a8505-203">**보호**\>**dkim** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-203">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="a8505-204">DKIM을 활성화 할 도메인을 선택한 다음 **DKIM 서명을 사용하여 이 도메인의 메시지 서명** 에 대해 **활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-204">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="a8505-205">각 사용자 지정 도메인에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-205">Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="a8505-206">PowerShell을 사용하여 사용자 지정 도메인에 DKIM 서명 사용</span><span class="sxs-lookup"><span data-stu-id="a8505-206">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="'이 도메인에 대해 저장된 DKIM 키가 없습니다.' 오류가 발생합니다.":::
> <span data-ttu-id="a8505-208">DKIM을 처음 구성하는 경우 '이 도메인에 대해 저장된 DKIM 키가 없습니다' 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-208">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain.'</span></span> <span data-ttu-id="a8505-209">아래 2단계의 명령을 완료하여(예: *Set-DkimSigningConfig -IDENTITY contoso.com -enabled $true*) 키를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-209">complete the command in step 2, below (for example, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) to see the key.</span></span>

1. <span data-ttu-id="a8505-210">[Exchange Online PowerShell에 연결합니다](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8505-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a8505-211">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="a8505-212">여기서 _도메인_ 은 DKIM 서명을 활성화하려는 사용자 지정 도메인의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="a8505-213">예를 들어 contoso.com 도메인의 경우</span><span class="sxs-lookup"><span data-stu-id="a8505-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="a8505-214">Microsoft 365에 DKIM 서명이 올바르게 구성되어 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a8505-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="a8505-215">다음 단계를 수행하여 DKIM을 올바르게 구성했는지 확인하기 전에 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-215">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="a8505-216">이를 통해 도메인에 대한 DKIM 정보가 네트워크 전체에 전파될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-216">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="a8505-217">Microsoft 365 DKIM 사용 가능한 도메인 내의 계정에서 outlook.com 또는 Hotmail.com과 같은 다른 전자 메일 계정으로 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="a8505-218">테스트 목적으로 aol.com 계정을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-218">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="a8505-219">SPF 검사가 통과되면 AOL에서 DKIM 검사를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-219">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="a8505-220">이렇게 하면 테스트가 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-220">This will nullify your test.</span></span>

- <span data-ttu-id="a8505-221">메시지를 열고 머리글을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-221">Open the message and look at the header.</span></span> <span data-ttu-id="a8505-222">메시지 머리글 보기에 대한 지침은 메시징 클라이언트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-222">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="a8505-223">Outlook에서 메시지 머리글을 보는 방법은 [Outlook에서 인터넷 메시지 머리글 보기](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-223">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="a8505-224">DKIM 서명 메시지에는 CNAME 항목을 게시할 때 정의한 호스트 이름과 도메인이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-224">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="a8505-225">메시지가 다음 예제와 같이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="a8505-225">The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="a8505-226">Authentication-Results 머리글을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-226">Look for the Authentication-Results header.</span></span> <span data-ttu-id="a8505-227">각 수신 서비스는 수신 메일을 스탬프 처리하기 위해 약간씩 다른 형식을 사용하지만 결과에는 **DKIM=pass** 또는 **DKIM=OK** 가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-227">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="a8505-228">Microsoft 365에서 두 개 이상의 사용자 지정 도메인에 대해 DKIM을 구성</span><span class="sxs-lookup"><span data-stu-id="a8505-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="a8505-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="a8505-230">나중에 다른 사용자 지정 도메인을 추가하기로 결정하고 새 도메인에 대해 DKIM을 활성화하려는 경우 각 도메인에 대해 이 문서의 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="a8505-231">특히 [DKIM을 수동으로 설정하려면 수행해야 할 작업](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)의 모든 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="a8505-232">사용자 지정 도메인에 대해 DKIM 서명 정책을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8505-232">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="a8505-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="a8505-234">서명 정책을 비활성화해도 DKIM이 완전히 비활성화되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="a8505-235">일정 시간이 지나면 Microsoft 365는 도메인에 대한 기본 Microsoft 365 정책을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="a8505-236">자세한 내용은 [DKIM 및 Microsoft 365의 기본 동작](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="a8505-237">Windows PowerShell을 사용하여 DKIM 서명 정책을 비활성화하려면</span><span class="sxs-lookup"><span data-stu-id="a8505-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="a8505-238">[Exchange Online PowerShell에 연결합니다](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8505-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a8505-239">DKIM 서명을 비활성화하려는 각 도메인에 대해 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="a8505-240">예:</span><span class="sxs-lookup"><span data-stu-id="a8505-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="a8505-241">또는</span><span class="sxs-lookup"><span data-stu-id="a8505-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="a8505-242">여기에서 _numbe_ r는 정책의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="a8505-243">예시:</span><span class="sxs-lookup"><span data-stu-id="a8505-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="a8505-244">DKIM 및 Microsoft 365의 기본 동작</span><span class="sxs-lookup"><span data-stu-id="a8505-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="a8505-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="a8505-246">DKIM을 사용하지 않도록 설정하면 Microsoft 365는 기본 도메인에 대해 1024 비트 DKIM 공개 키와 데이터 센터에 내부적으로 저장되는 관련 개인 키를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="a8505-247">기본적으로 Microsoft 365는 정책이 없는 도메인에 대해 기본 서명 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="a8505-248">즉, DKIM을 직접 설정하지 않으면 Microsoft 365는 도메인에 DKIM을 사용하기 위해 만든 기본 정책과 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="a8505-249">또한 DKIM 서명을 사용하도록 설정 한 후 다시 사용하지 않도록 설정할 경우 일정 시간이 지나면 Microsoft 365가 도메인에 대해 Microsoft 365 기본 정책을 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="a8505-250">다음 예제에서는 fabrikam.com용 DKIM이 도메인 관리자가 아닌 Microsoft 365에서 활성화되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="a8505-251">이는 필수적인 CNAME이 DNS에 존재하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="a8505-252">이 도메인의 전자 메일에 대한 DKIM 서명은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="a8505-253">이 예제에서 도메인 관리자가 fabrikam.com에 대한 DKIM 서명을 활성화한 경우 호스트 이름과 도메인에는 CNAME이 가리키는 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="a8505-254">결국 Microsoft 365에서 보낸 모든 단일 메시지는 DKIM 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="a8505-255">DKIM을 직접 활성화하는 경우 도메인은 보낸 사람:주소의 도메인 (이 경우 fabrikam.com)과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="a8505-256">직접 활성화하지 않는 경우 맞추는 대신 사용자 조직의 초기 도메인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="a8505-257">초기 도메인을 확인하는 방법에 대한 자세한 내용은 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="a8505-258">타사 서비스에서 사용자 지정 도메인을 대신하여 이메일을 보내거나 스푸핑할 수 있도록 DKIM을 설정</span><span class="sxs-lookup"><span data-stu-id="a8505-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="a8505-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="a8505-260">일부 대량 전자 메일 서비스 공급자 또는 소프트웨어를 서비스로 제공하는 공급자는 서비스에서 보낸 전자 메일에 대해 DKIM 키를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="a8505-261">필수 DNS 레코드를 설정하기 위해서는 본인과 타사 간의 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="a8505-262">일부 타사 서버에는 다양한 선택기를 포함한 고유 CNAME 레코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-262">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="a8505-263">두 조직이 정확히 동일한 방식으로 이 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-263">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="a8505-264">그 대신 프로세스는 전적으로 조직에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-264">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="a8505-265">contoso.com 및 bulkemailprovider.com에 대해 올바르게 구성된 DKIM을 보여주는 메시지의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-265">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="a8505-266">이 예제에서는 이 결과를 얻기 위해 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-266">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="a8505-267">대량 전자 메일 공급자가 Contoso에 공개 DKIM 키를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-267">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="a8505-268">Contoso는 DKIM 키를 해당 DNS 레코드에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-268">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="a8505-269">전자 메일을 보낼 때 대량 전자 메일 공급자는 해당하는 개인 키로 키에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-269">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="a8505-270">이렇게하면 대량 전자 메일 공급자가 메시지 머리글에 DKIM 서명을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-270">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="a8505-271">수신 이메일 시스템은 메시지의 From:(5322.From) 주소에서 도메인에 대해 DKIM-Signature d=\<domain\> 값을 인증하여 DKIM 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-271">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="a8505-272">이 예제에서 값은 다음과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-272">In this example, the values match:</span></span>

   > <span data-ttu-id="a8505-273">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="a8505-273">sender@**contoso.com**</span></span>

   > <span data-ttu-id="a8505-274">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="a8505-274">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="a8505-275">전자 메일을 보내지 않는 도메인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-275">Identify domains that do not send email</span></span>

<span data-ttu-id="a8505-276">조직은 도메인이 해당 도메인에 대해 DKIM 레코드에 `v=DKIM1; p=`을(를) 지정하여 전자 메일을 보내지 않는지 명시적으로 명시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-276">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="a8505-277">이것은 전자 메일 서버를 수신할 때 도메인에 대한 유효한 공용 키가 없으며 해당 도메인에서 왔다고 주장하는 전자 메일은 거부되어야 한다는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-277">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="a8505-278">와일드카드 DKIM을 사용하여 각 도메인 및 하위 도메인에 대해 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-278">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="a8505-279">예를 들어, DKIM 레코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-279">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="a8505-280">다음 단계: Microsoft 365에 대한 DKIM을 설정한 후</span><span class="sxs-lookup"><span data-stu-id="a8505-280">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="a8505-281"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="a8505-281"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="a8505-282">DKIM은 스푸핑을 방지하도록 설계되었지만 SPF 및 DMARC에서 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-282">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="a8505-283">DKIM을 설정한 후에 SPF를 아직 설정하지 않은 경우 설정을 수행해야합니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-283">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="a8505-284">SPF를 빠르게 도입하여 신속하게 구성하려면 [스푸핑 방지를 위해 Microsoft 365에서 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-284">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="a8505-285">Microsoft 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Microsoft 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-285">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="a8505-286">다음으로 [DMARC를 사용하여 전자 메일 유효성 검사](use-dmarc-to-validate-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8505-286">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="a8505-287">[스팸 방지 메시지 헤더](anti-spam-message-headers.md)에는 Microsoft 365에서 DKIM 검사에 사용하는 구문 및 헤더 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8505-287">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="a8505-288">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a8505-288">More information</span></span>

<span data-ttu-id="a8505-289">[회전-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)을 통한 키 회전</span><span class="sxs-lookup"><span data-stu-id="a8505-289">Key rotation via PowerShell [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
