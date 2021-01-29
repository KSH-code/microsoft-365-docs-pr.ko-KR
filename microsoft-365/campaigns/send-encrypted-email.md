---
title: 암호화된 전자 메일 보내기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook을 사용하여 암호화된 전자 메일을 보내는 방법을 배워야 합니다.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044219"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="5b0dd-103">중요한 전자 메일을 암호화하거나 레이블을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="5b0dd-104">데이터 및 캠페인 정보는 중요하고 종종 기밀입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="5b0dd-105">암호화 및 민감도 레이블을 사용하여 이 중요한 정보를 보호하여 사용자와 전자 메일 받는 사람이 정보를 필요한 민감도로 취급할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="5b0dd-106">모범 사례</span><span class="sxs-lookup"><span data-stu-id="5b0dd-106">Best practices</span></span>

<span data-ttu-id="5b0dd-107">기밀 또는 중요한 정보가 있는 전자 메일을 보내기 전에 다음을 켜는 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="5b0dd-108">**암호화:** 전자 메일의 정보 개인 정보를 보호하기 위해 전자 메일을 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="5b0dd-109">전자 메일 메시지를 암호화하면 읽을 수 있는 일반 텍스트에서 스크램블된 키프 텍스트로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="5b0dd-110">메시지를 암호화하는 데 사용되는 공개 키와 일치하는 개인 키가 있는 받는 사람만 메시지를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="5b0dd-111">그러나 해당 개인 키가 없는 받는 사람은 검색할 수 없는 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="5b0dd-112">관리자는 특정 조건을 충족하는 메시지를 자동으로 암호화하는 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="5b0dd-113">예를 들어 관리자는 조직 외부로 전송된 모든 메시지 또는 특정 단어나 구를 언급하는 모든 메시지를 암호화하는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="5b0dd-114">암호화 규칙은 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="5b0dd-115">**민감도 레이블:** 캠페인에서 파일 및 전자 메일에 적용할 수 있는 민감도 레이블을 설정하여 캠페인의 정보 보호 정책을 준수하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="5b0dd-116">레이블을 설정하면 레이블이 전송된 경우에도(예: 메시지에 헤더로 표시) 전자 메일과 함께 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![레이블 및 암호화에 대한 설명선이 있는 전자 메일 다이어그램](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="5b0dd-118">설정하기</span><span class="sxs-lookup"><span data-stu-id="5b0dd-118">Set it up</span></span>

<span data-ttu-id="5b0dd-119">미리 정의된 규칙을 충족하지 않는 메시지를 암호화하거나 관리자가 규칙을 설정하지 않은 경우 메시지를 보내기 전에 다양한 암호화 규칙을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="5b0dd-120">Outlook 2013 또는 2016 또는 Mac용 Outlook 2016에서 암호화된 메시지를 보내기 위해 옵션 > 사용 권한을 선택한 다음 필요한 보호 옵션을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="5b0dd-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="5b0dd-121">웹에서 Outlook의 보호 단추를 선택하여  암호화된 메시지를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="5b0dd-122">자세한 내용은 PC용 Outlook에서 암호화된 메시지 보내기, 보기 및 [회신을 참조하세요.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="5b0dd-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="5b0dd-123">관리자 설정</span><span class="sxs-lookup"><span data-stu-id="5b0dd-123">Admin settings</span></span>

<span data-ttu-id="5b0dd-124">[Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)전자 메일 암호화에서 전자 메일 암호화를 설정하는 방법을 모두 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="5b0dd-125">전자 메일 메시지 자동 암호화</span><span class="sxs-lookup"><span data-stu-id="5b0dd-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="5b0dd-126">관리자는 캠페인에서 보내고 받은 전자 메일 메시지를 자동으로 보호하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="5b0dd-127">발신 전자 메일 메시지를 암호화하고 조직 내부에서 오는 암호화된 메시지에서 암호화를 제거하거나 조직에서 보낸 암호화된 메시지에 대한 응답에서 암호화를 제거하는 규칙을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="5b0dd-128">새 Office 365 OME(메시지 암호화) 기능을 사용하여 전자 메일 메시지를 암호화하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="5b0dd-129">EAC(Exchange 관리 센터)를 사용하여 새 OME 기능을 사용하여 메시지 암호화를 트리거하기 위한 메일 흐름 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="5b0dd-130">웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="5b0dd-131">관리 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="5b0dd-132">In the admin center, choose **Admin centers > Exchange.**</span><span class="sxs-lookup"><span data-stu-id="5b0dd-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="5b0dd-133">자세한 내용은 전자 메일 메시지를 암호화하는 메일 흐름 [규칙 정의를 참조하십시오.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)</span><span class="sxs-lookup"><span data-stu-id="5b0dd-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="5b0dd-134">암호화 메시지 브랜드</span><span class="sxs-lookup"><span data-stu-id="5b0dd-134">Brand your encryption messages</span></span>

<span data-ttu-id="5b0dd-135">캠페인 브랜드를 적용하여 전자 메일 메시지의 모양과 텍스트를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0dd-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="5b0dd-136">자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="5b0dd-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
