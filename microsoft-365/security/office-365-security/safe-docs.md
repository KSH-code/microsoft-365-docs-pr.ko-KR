---
title: Office 365용 Microsoft Defender의 안전 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 금고 문서 또는 Microsoft 365 E5 문서에 대해 Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1049543b11ad14eeeed596367228f025cc8edd65
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054435"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="80c65-103">Microsoft 365 E5에서 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="80c65-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80c65-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="80c65-104">**Applies to**</span></span>
- [<span data-ttu-id="80c65-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80c65-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="80c65-106">금고 문서는 Microsoft 365 E5 또는 Microsoft 365 E5 Security [Microsoft Defender for Endpoint를](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 사용하여 보호된 보기 또는 [Application Guard에서](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)열 수 있는 문서 및 파일을 검사하는 Office. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="80c65-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80c65-107">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="80c65-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80c65-108">금고 문서는 라이선스가 없는  사용자만 사용할 *Microsoft 365 E5* Microsoft 365 E5 Security 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="80c65-109">이러한 라이선스는 Microsoft Defender for Office 365 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="80c65-110">금고 문서는 엔터프라이즈용 Microsoft 365 앱(Office 365 ProPlus) 버전 2004 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="80c65-111"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="80c65-112">첨부 파일 **페이지로** 직접 금고 를 <https://security.microsoft.com/safeattachmentv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="80c65-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="80c65-113">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80c65-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="80c65-114">이 문서의 절차를 **Exchange Online** 수행하려면 먼저 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="80c65-115">문서 금고 구성하려면 조직 관리 또는 보안 관리자 역할  그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="80c65-116">문서 설정에 금고 읽기 전용으로 액세스하려면 전역 읽기 그룹 또는  보안 읽기 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="80c65-117">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80c65-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="80c65-118">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80c65-119">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80c65-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="80c65-120">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="80c65-121">Microsoft는 데이터를 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="80c65-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="80c65-122">보호를 유지하기 위해 금고 문서를 분석하기 위해 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 클라우드로 파일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="80c65-123">끝점용 Microsoft Defender가 데이터를 처리하는 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 [보호용 Microsoft Defender에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="80c65-124">금고 전송된 파일은 분석에 필요한 시간(일반적으로 24시간 미만)이 지난 시간 동안 Defender에 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="80c65-125">다음 Microsoft 365 Defender 사용하여 문서 금고 구성</span><span class="sxs-lookup"><span data-stu-id="80c65-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="80c65-126">Microsoft 365 Defender 포털을 열고 전자 메일 & **공동** 작업 정책 & 규칙 위협 정책 \>  \>  \>  \> **섹션(첨부 금고 로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="80c65-126">Open the Microsoft 365 Defender portal and go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="80c65-127">첨부 **금고 페이지에서** 전역 설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="80c65-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="80c65-128">전역 **설정** 플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="80c65-129">**금고** 클라이언트에 대한 Office 설정 : 토글을 오른쪽으로 이동하여 기능을 ![ 켜기: ](../../media/scc-toggle-on.png) 토글합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="80c65-130">**파일을 악성으로** 식별한 문서가 금고 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용 : 이 옵션을 해제한 후(토글을 왼쪽으로 두기: 토글 해제) 하는 것이 ![ 좋습니다. ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="80c65-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="80c65-131">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-131">When you're finished, click **Save**.</span></span>

   ![금고 첨부 파일 페이지에서 전역 설정을 선택한 금고 문서화합니다.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="80c65-133">PowerShell Exchange Online 사용하여 문서 금고 구성</span><span class="sxs-lookup"><span data-stu-id="80c65-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="80c65-134">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="80c65-135">_EnableSafeDocs_ 매개 변수는 전체 조직에 대해 금고 또는 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="80c65-136">_AllowSafeDocsOpen_ 매개 변수는 문서가 악의적인 것으로 확인된 경우 사용자가 보호된 보기(즉, 문서를 여는 경우)를 허용하거나 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="80c65-137">이 예에서는 금고 문서에 대해 문서를 저장하고 사용자가 보호된 보기에서 악의적인 것으로 확인된 문서를 열지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="80c65-138">구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="80c65-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="80c65-139">감사 기능을 사용하도록 설정하기 위해 끝점 서비스용 Microsoft Defender에 온보딩</span><span class="sxs-lookup"><span data-stu-id="80c65-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="80c65-140">끝점용 Microsoft Defender를 배포하려면 다양한 배포 단계를 거치야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="80c65-141">온보드 후 사이트 포털에서 감사 기능을 구성할 Microsoft 365 Defender 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="80c65-142">자세한 내용은 [끝점 서비스용 Microsoft Defender에 온보딩을 참조합니다.](/microsoft-365/security/defender-endpoint/onboarding)</span><span class="sxs-lookup"><span data-stu-id="80c65-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="80c65-143">추가 도움이 필요한 경우 Endpoint 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조합니다.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="80c65-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="80c65-144">작동 여부는 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="80c65-144">How do I know this worked?</span></span>

<span data-ttu-id="80c65-145">문서를 사용하도록 설정하고 구성한 금고 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="80c65-146">Microsoft 365 Defender 포털에서 전자 메일 **& 공동** 작업 정책 & 규칙 위협 정책 정책 \>  \>  \>  \> **섹션금고** \>    첨부 파일 전역 설정으로 이동한 후 Office 클라이언트에 대해 금고 문서 켜기 및 문서에서 파일을 악성 설정으로 식별한 경우에도 사용자가 금고 보기를 클릭할 수 있도록 허용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="80c65-147">PowerShell에서 Exchange Online 명령을 실행하고 속성 값을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="80c65-148">다음 파일은 문서 보호를 테스트하는 금고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="80c65-149">이러한 문서는 맬웨어 방지 EICAR.TXT 바이러스 백신 솔루션을 테스트하기 위한 파일과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="80c65-150">파일은 해로운 파일은 아니며 문서 보호를 금고 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="80c65-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="80c65-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="80c65-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="80c65-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="80c65-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="80c65-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="80c65-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
