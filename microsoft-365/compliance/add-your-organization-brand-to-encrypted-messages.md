---
title: 암호화된 메시지에 조직 브랜드 추가
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 전역 Office 365 조직의 브랜드를 암호화 포털의 콘텐츠와 함께 암호화된 전자 메일 메시지에 적용하는 & 방법을 알아보겠습니다.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394716"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="5b48a-103">비즈니스용 메시지 암호화 암호화 Microsoft 365 조직 브랜드 추가</span><span class="sxs-lookup"><span data-stu-id="5b48a-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="5b48a-104">회사 브랜드를 적용하여 조직의 전자 메일 메시지와 암호화 포털의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="5b48a-105">시작하기 전에 먼저 직장 또는 학교 계정에 전역 관리자 권한을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="5b48a-106">이러한 사용 권한이 있는 경우 Get-OMEConfiguration 및 Set-OMEConfiguration Windows PowerShell cmdlet을 사용하여 암호화된 전자 메일 메시지의 이러한 부분을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="5b48a-107">소개 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-107">Introductory text</span></span>

- <span data-ttu-id="5b48a-108">고지서 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-108">Disclaimer text</span></span>

- <span data-ttu-id="5b48a-109">조직의 개인 정보 취급 방침 URL</span><span class="sxs-lookup"><span data-stu-id="5b48a-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="5b48a-110">OME 포털의 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-110">Text in the OME portal</span></span>

- <span data-ttu-id="5b48a-111">전자 메일 메시지 및 OME 포털에 나타나는 로고 또는 로고를 사용할지 여부</span><span class="sxs-lookup"><span data-stu-id="5b48a-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="5b48a-112">전자 메일 메시지 및 OME 포털의 배경색</span><span class="sxs-lookup"><span data-stu-id="5b48a-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="5b48a-113">언제든지 기본 모양과 느낌으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="5b48a-114">더 많은 제어를 원할 경우 조직에서 Office 365 고급 메시지 암호화 암호화된 전자 메일에 대한 여러 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="5b48a-115">이러한 템플릿을 사용하여 최종 사용자 환경의 일부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="5b48a-116">예를 들어 받는 사람이 Google, Yahoo 및 Microsoft 계정을 사용하여 암호화 포털에 로그인할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="5b48a-117">서식 파일을 사용하여 다음의 여러 사용 사례를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="5b48a-118">재무, 영업 등의 개별 부서</span><span class="sxs-lookup"><span data-stu-id="5b48a-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="5b48a-119">다른 제품</span><span class="sxs-lookup"><span data-stu-id="5b48a-119">Different products</span></span>

- <span data-ttu-id="5b48a-120">다양한 지리적 지역 또는 국가</span><span class="sxs-lookup"><span data-stu-id="5b48a-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="5b48a-121">전자 메일이 해지될 수 있도록 허용할지 여부</span><span class="sxs-lookup"><span data-stu-id="5b48a-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="5b48a-122">외부 받는 사람에게 보낸 전자 메일이 지정된 일 수 후에 만료될지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="5b48a-123">템플릿을 만든 후 메일 흐름 규칙을 사용하여 암호화된 전자 메일에 Exchange 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="5b48a-124">이 Office 365 고급 메시지 암호화 경우 이러한 템플릿을 사용하여 브랜드한 모든 전자 메일을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="5b48a-125">OME 브랜랜드 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="5b48a-125">Work with OME branding templates</span></span>

<span data-ttu-id="5b48a-126">브랜드 템플릿 내에서 여러 기능을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="5b48a-127">기본 템플릿은 수정할 수 있지만 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="5b48a-128">고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고 수정하고 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="5b48a-129">브랜 Windows PowerShell 한 번씩 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="5b48a-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 만든 기본 브랜징 템플릿 또는 사용자 지정 브랜징 템플릿을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="5b48a-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 새 브랜드 템플릿인 고급 메시지 암호화만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="5b48a-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - 사용자 지정 브랜징 템플릿인 고급 메시지 암호화만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="5b48a-133">기본 브랜드 템플릿은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="5b48a-134">OME 브랜랜드 템플릿 수정</span><span class="sxs-lookup"><span data-stu-id="5b48a-134">Modify an OME branding template</span></span>

<span data-ttu-id="5b48a-135">이 Windows PowerShell 사용하여 한 번의 브랜드 템플릿을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="5b48a-136">고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고 수정하고 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="5b48a-137">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b48a-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5b48a-138">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5b48a-139">[Set-OMEConfiguration에](/powershell/module/exchange/Set-OMEConfiguration) 설명된 Set-OMEConfiguration cmdlet을 사용하거나 다음 그래픽 및 표를 사용하여 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![사용자 지정 가능한 전자 메일 파트](../media/ome-template-breakout.png)

|<span data-ttu-id="5b48a-141">**암호화 환경에서 사용자 지정하려는 기능**</span><span class="sxs-lookup"><span data-stu-id="5b48a-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="5b48a-142">**다음 명령 사용**</span><span class="sxs-lookup"><span data-stu-id="5b48a-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b48a-143">배경색</span><span class="sxs-lookup"><span data-stu-id="5b48a-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="5b48a-144">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="5b48a-145">배경색에 대한 자세한 내용은 이 문서 부분의 [배경색](#background-color-reference) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="5b48a-146">로고</span><span class="sxs-lookup"><span data-stu-id="5b48a-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="5b48a-147">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="5b48a-148">지원되는 파일 형식: .png, .jpg, .bmp 또는 .tiff</span><span class="sxs-lookup"><span data-stu-id="5b48a-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="5b48a-149">로고 파일의 최적 크기: 40KB 미만</span><span class="sxs-lookup"><span data-stu-id="5b48a-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="5b48a-150">로고 이미지의 최적 크기: 170x70 픽셀</span><span class="sxs-lookup"><span data-stu-id="5b48a-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="5b48a-151">이미지가 이러한 크기를 초과하면 서비스에서 포털에 표시하기 위해 로고 크기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="5b48a-152">서비스는 그래픽 파일 자체를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="5b48a-153">최상의 결과를 얻기 위해 최적의 크기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="5b48a-154">보낸 사람 이름 및 전자 메일 주소 옆의 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5b48a-155">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="5b48a-156">"메시지 읽기" 단추에 나타나는 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5b48a-157">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="5b48a-158">"메시지 읽기" 단추 아래에 나타나는 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5b48a-159">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="5b48a-160">개인 정보 취급 방침 링크의 URL</span><span class="sxs-lookup"><span data-stu-id="5b48a-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="5b48a-161">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="5b48a-162">암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문</span><span class="sxs-lookup"><span data-stu-id="5b48a-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="5b48a-163">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="5b48a-164">암호화된 메일 보기 포털 위쪽에 표시되는 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="5b48a-165">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="5b48a-166">이 사용자 지정 서식 파일에서 일회용 암호로 인증을 사용하도록 설정하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="5b48a-167">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-167">**Examples:**</span></span> <br/><span data-ttu-id="5b48a-168">이 사용자 지정 서식 파일에서 일회용 암호를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="5b48a-169">이 사용자 지정 서식 파일에서 일회용 암호를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5b48a-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="5b48a-170">이 사용자 지정 서식 파일에서 Microsoft, Google 또는 Yahoo ID로 인증을 사용하도록 설정하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="5b48a-171">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-171">**Examples:**</span></span> <br/><span data-ttu-id="5b48a-172">이 사용자 지정 서식 파일에서 공유 ID를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="5b48a-173">이 사용자 지정 서식 파일에서 공유 ID를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5b48a-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="5b48a-174">OME 브랜랜드 템플릿 만들기(고급 메시지 암호화)</span><span class="sxs-lookup"><span data-stu-id="5b48a-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="5b48a-175">이 Office 365 고급 메시지 암호화 [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet을 사용하여 조직에 대한 사용자 지정 브랜징 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="5b48a-176">템플릿을 만든 후 Modify an OME branding template 에 설명된 Set-OMEConfiguration cmdlet을 사용하여 [템플릿을 수정합니다.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="5b48a-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="5b48a-177">여러 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-177">You can create multiple templates.</span></span>

<span data-ttu-id="5b48a-178">새 사용자 지정 브랜징 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="5b48a-179">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b48a-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5b48a-180">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5b48a-181">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet을 사용하여 새 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="5b48a-182">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="5b48a-183">기본 브랜드 템플릿을 원래 값으로 반환</span><span class="sxs-lookup"><span data-stu-id="5b48a-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="5b48a-184">브랜드 사용자 지정 등을 포함하여 기본 템플릿에서 모든 수정 내용을 제거하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="5b48a-185">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b48a-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5b48a-186">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5b48a-187">**Set-OMEConfiguration 에** 설명된 바와 같이 [Set-OMEConfiguration cmdlet을 사용 합니다.](/powershell/module/exchange/Set-OMEConfiguration)</span><span class="sxs-lookup"><span data-stu-id="5b48a-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="5b48a-188">DisclaimerText, EmailText 및 PortalText 값에서 조직의 브랜드 사용자 지정을 제거하려면 값을 빈 문자열인 로 `""` 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b48a-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="5b48a-189">로고와 같은 모든 이미지 값에 대해 값을 로  `"$null"` 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="5b48a-190">다음 표에는 암호화 사용자 지정 옵션 기본값이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="5b48a-191">암호화 환경의 이 기능을 기본 텍스트 및 이미지로 되돌리려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="5b48a-192">다음 명령 사용</span><span class="sxs-lookup"><span data-stu-id="5b48a-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5b48a-193">암호화된 전자 메일 메시지와 함께 제공된 기본 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="5b48a-194">암호화된 메시지를 보기 위한 지침 위에 표시되는 기본 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="5b48a-195">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="5b48a-196">암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문</span><span class="sxs-lookup"><span data-stu-id="5b48a-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="5b48a-197">**예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="5b48a-198">암호화된 메일 보기 포털 위쪽에 표시되는 텍스트</span><span class="sxs-lookup"><span data-stu-id="5b48a-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="5b48a-199">**기본값으로 되돌리기 예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="5b48a-200">로고</span><span class="sxs-lookup"><span data-stu-id="5b48a-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="5b48a-201">**기본값으로 되돌리기 예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="5b48a-202">배경색</span><span class="sxs-lookup"><span data-stu-id="5b48a-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="5b48a-203">**기본값으로 되돌리기 예제:**</span><span class="sxs-lookup"><span data-stu-id="5b48a-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="5b48a-204">사용자 지정 브랜징 템플릿 제거(고급 메시지 암호화)</span><span class="sxs-lookup"><span data-stu-id="5b48a-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="5b48a-205">만든 브랜디드 템플릿만 제거하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="5b48a-206">기본 브랜드 템플릿은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="5b48a-207">사용자 지정 브랜징 서식 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="5b48a-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="5b48a-208">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b48a-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5b48a-209">지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5b48a-210">**Remove-OMEConfiguration** cmdlet은 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="5b48a-211">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="5b48a-212">자세한 내용은 [Remove-OMEConfiguration을 참조하십시오.](/powershell/module/exchange/remove-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="5b48a-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="5b48a-213">암호화된 Exchange 사용자 지정 브랜더를 적용하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5b48a-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="5b48a-214">기본 템플릿을 수정하거나 새 브랜더링 템플릿을 만든 후 특정 조건에 Exchange 사용자 지정 브랜더링을 적용하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="5b48a-215">이러한 규칙은 다음과 같은 시나리오에서 사용자 지정 브랜드를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="5b48a-216">최종 사용자가 웹에서 Outlook 또는 Outlook 전자 메일을 수동으로 암호화한 경우 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="5b48a-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="5b48a-217">전자 메일이 Exchange 메일 흐름 규칙 또는 데이터 손실 방지 정책에 의해 자동으로 암호화된 경우</span><span class="sxs-lookup"><span data-stu-id="5b48a-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="5b48a-218">암호화를 적용하는 Exchange 메일 흐름 규칙을 만드는 방법에 대한 자세한 내용은 [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="5b48a-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="5b48a-219">웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 에 [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="5b48a-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5b48a-220">관리 **타일을** 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="5b48a-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5b48a-221">in the Microsoft 365 admin center, choose **Admin centers** \> **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="5b48a-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5b48a-222">EAC에서 메일 흐름 **규칙으로** 이동하고 새 새로 만들기 아이콘 새 규칙 \>   ![ 만들기 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b48a-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="5b48a-223">EAC 사용에 대한 자세한 내용은 에서 Exchange [관리 센터를 Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="5b48a-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="5b48a-224">**이름에** 규칙의 이름(예: 영업 부서의 브랜드)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="5b48a-225">다음의 **경우** 이 규칙  적용에서 보낸 사람이 조직 내부에 있는 조건 및 사용 가능한 조건 목록에서 원하는 기타 조건을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="5b48a-226">예를 들어 다음에 특정 브랜드 템플릿을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="5b48a-227">재무 부서의 구성원이 보낸 모든 암호화된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="5b48a-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="5b48a-228">"외부" 또는 "파트너"와 같은 특정 키워드를 사용하여 전송된 암호화된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="5b48a-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="5b48a-229">특정 도메인으로 전송된 암호화된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="5b48a-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="5b48a-230">다음 **작업에서** 메시지 보안 수정 **OME** 메시지에 사용자 지정 \> **브랜드 적용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b48a-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="5b48a-231">그런 다음 드롭다운에서 브랜드 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="5b48a-232">(선택 사항) 암호화 및 사용자 지정 브랜드를 적용하도록 메일 흐름 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="5b48a-233">다음 **작업에서** **메시지** 보안 수정을 선택한 다음 메시지 보안 및 권한 **Office 365 메시지 암호화 적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b48a-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="5b48a-234">목록에서 RMS 템플릿을 선택하고 **저장을** 선택한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5b48a-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="5b48a-235">템플릿 목록에는 기본 서식 파일 및 옵션과 만든 모든 사용자 지정 템플릿이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="5b48a-236">목록이 비어 있는 경우 새 기능을 Office 365 메시지 암호화 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="5b48a-237">자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="5b48a-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="5b48a-238">기본 템플릿에 대한 자세한 내용은 Azure Information Protection용 템플릿 구성 및 [관리를 참조하세요.](/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="5b48a-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="5b48a-239">전달 금지 **옵션에** 대한 자세한 내용은 전자 메일에 [대해 전달 금지 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="5b48a-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="5b48a-240">암호화 전용 **옵션에** 대한 자세한 내용은 전자 메일에 대한 [암호화 전용 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="5b48a-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="5b48a-241">다른 **작업을 지정하려는** 경우 작업 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="5b48a-242">배경색 참조</span><span class="sxs-lookup"><span data-stu-id="5b48a-242">Background color reference</span></span>

<span data-ttu-id="5b48a-243">배경색에 사용할 수 있는 색 이름은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="5b48a-244">색 이름 대신 16진수 코드 값(16진수)을 사용할 #RRGGBB.</span><span class="sxs-lookup"><span data-stu-id="5b48a-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="5b48a-245">색 이름에 해당하는 16진수 코드 값을 사용할 수도, 사용자 지정 16진수 코드 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="5b48a-246">16진수 코드 값을 인용 부호(예: )로 `"#f0f8ff"` 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="5b48a-247">사용 가능한 배경색 이름과 해당 16진수 코드 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b48a-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="5b48a-248">**색 이름**</span><span class="sxs-lookup"><span data-stu-id="5b48a-248">**Color name**</span></span>|<span data-ttu-id="5b48a-249">**색 코드**</span><span class="sxs-lookup"><span data-stu-id="5b48a-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="5b48a-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="5b48a-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="5b48a-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="5b48a-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="5b48a-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="5b48a-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="5b48a-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="5b48a-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="5b48a-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="5b48a-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="5b48a-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="5b48a-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="5b48a-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="5b48a-257">#000000</span><span class="sxs-lookup"><span data-stu-id="5b48a-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="5b48a-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="5b48a-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="5b48a-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="5b48a-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="5b48a-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="5b48a-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="5b48a-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="5b48a-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="5b48a-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="5b48a-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="5b48a-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="5b48a-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="5b48a-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="5b48a-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="5b48a-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="5b48a-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="5b48a-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="5b48a-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="5b48a-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="5b48a-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="5b48a-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="5b48a-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="5b48a-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="5b48a-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="5b48a-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="5b48a-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="5b48a-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="5b48a-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="5b48a-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="5b48a-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="5b48a-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="5b48a-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="5b48a-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="5b48a-275">#006400</span><span class="sxs-lookup"><span data-stu-id="5b48a-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="5b48a-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="5b48a-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="5b48a-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="5b48a-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="5b48a-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="5b48a-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="5b48a-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="5b48a-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="5b48a-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="5b48a-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="5b48a-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="5b48a-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="5b48a-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="5b48a-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="5b48a-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="5b48a-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="5b48a-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="5b48a-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="5b48a-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="5b48a-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="5b48a-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="5b48a-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="5b48a-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="5b48a-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="5b48a-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="5b48a-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="5b48a-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="5b48a-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="5b48a-290">#696969</span><span class="sxs-lookup"><span data-stu-id="5b48a-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="5b48a-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="5b48a-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="5b48a-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="5b48a-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="5b48a-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="5b48a-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="5b48a-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="5b48a-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="5b48a-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="5b48a-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="5b48a-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="5b48a-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="5b48a-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="5b48a-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="5b48a-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="5b48a-300">#808080</span><span class="sxs-lookup"><span data-stu-id="5b48a-300">#808080</span></span>|
|`green`|<span data-ttu-id="5b48a-301">#008000</span><span class="sxs-lookup"><span data-stu-id="5b48a-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="5b48a-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="5b48a-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="5b48a-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="5b48a-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="5b48a-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="5b48a-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="5b48a-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="5b48a-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="5b48a-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="5b48a-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="5b48a-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="5b48a-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="5b48a-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="5b48a-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="5b48a-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="5b48a-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="5b48a-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="5b48a-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="5b48a-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="5b48a-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="5b48a-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="5b48a-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="5b48a-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="5b48a-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="5b48a-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="5b48a-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="5b48a-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="5b48a-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="5b48a-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="5b48a-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="5b48a-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="5b48a-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="5b48a-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="5b48a-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="5b48a-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="5b48a-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="5b48a-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="5b48a-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="5b48a-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="5b48a-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="5b48a-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="5b48a-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="5b48a-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="5b48a-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="5b48a-324">#778899</span><span class="sxs-lookup"><span data-stu-id="5b48a-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="5b48a-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="5b48a-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="5b48a-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="5b48a-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="5b48a-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="5b48a-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="5b48a-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="5b48a-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="5b48a-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="5b48a-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="5b48a-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="5b48a-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="5b48a-331">#800000</span><span class="sxs-lookup"><span data-stu-id="5b48a-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="5b48a-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="5b48a-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="5b48a-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="5b48a-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="5b48a-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="5b48a-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="5b48a-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="5b48a-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="5b48a-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="5b48a-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="5b48a-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="5b48a-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="5b48a-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="5b48a-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="5b48a-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="5b48a-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="5b48a-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="5b48a-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="5b48a-341">#191970</span><span class="sxs-lookup"><span data-stu-id="5b48a-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="5b48a-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="5b48a-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="5b48a-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="5b48a-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="5b48a-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="5b48a-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="5b48a-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="5b48a-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="5b48a-346">#000080</span><span class="sxs-lookup"><span data-stu-id="5b48a-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="5b48a-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="5b48a-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="5b48a-348">#808000</span><span class="sxs-lookup"><span data-stu-id="5b48a-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="5b48a-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="5b48a-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="5b48a-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="5b48a-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="5b48a-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="5b48a-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="5b48a-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="5b48a-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="5b48a-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="5b48a-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="5b48a-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="5b48a-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="5b48a-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="5b48a-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="5b48a-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="5b48a-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="5b48a-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="5b48a-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="5b48a-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="5b48a-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="5b48a-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="5b48a-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="5b48a-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="5b48a-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="5b48a-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="5b48a-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="5b48a-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="5b48a-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="5b48a-363">#800080</span><span class="sxs-lookup"><span data-stu-id="5b48a-363">#800080</span></span>|
|`red`|<span data-ttu-id="5b48a-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="5b48a-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="5b48a-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="5b48a-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="5b48a-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="5b48a-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="5b48a-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="5b48a-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="5b48a-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="5b48a-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="5b48a-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="5b48a-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="5b48a-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="5b48a-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="5b48a-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="5b48a-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="5b48a-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="5b48a-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="5b48a-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="5b48a-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="5b48a-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="5b48a-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="5b48a-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="5b48a-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="5b48a-376">#708090</span><span class="sxs-lookup"><span data-stu-id="5b48a-376">#708090</span></span>|
|`snow`|<span data-ttu-id="5b48a-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="5b48a-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="5b48a-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="5b48a-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="5b48a-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="5b48a-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="5b48a-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="5b48a-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="5b48a-381">#008080</span><span class="sxs-lookup"><span data-stu-id="5b48a-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="5b48a-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="5b48a-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="5b48a-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="5b48a-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="5b48a-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="5b48a-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="5b48a-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="5b48a-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="5b48a-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="5b48a-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="5b48a-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="5b48a-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="5b48a-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="5b48a-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="5b48a-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="5b48a-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="5b48a-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="5b48a-390">#9acd32</span></span>|