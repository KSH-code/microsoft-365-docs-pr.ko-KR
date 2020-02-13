---
title: Office 365 ATP의 안전한 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 ATP의 안전한 문서에 대해 알아봅니다.
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960358"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="ae4fe-103">Office 365 Advanced Threat Protection의 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="ae4fe-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="ae4fe-104">안전한 문서는 [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 을 사용 하 여 [제한 된 보기](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)에서 열린 문서와 파일을 검색 하는 Office 365 ATP (Advanced threat protection)의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ae4fe-105">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="ae4fe-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ae4fe-106">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ae4fe-107">Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ae4fe-108">이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="ae4fe-109">안전한 문서를 사용 하도록 설정 하 고 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ae4fe-110">보안 & 준수 센터의 역할 그룹에 대 한 자세한 내용은 [Permissions in The Office 365 Security & 준수 센터](permissions-in-the-security-and-compliance-center.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ae4fe-111">Office 365 보안 & 준수 센터를 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="ae4fe-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ae4fe-112">에서 <https://protection.office.com>Office 365 보안 & 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="ae4fe-113">**위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="ae4fe-114">**Office 응용 프로그램에서 제한 된 보기를 열 수 있도록 파일을 신뢰 하는 경우 사용자가 안전 하 게** 보호 섹션을 유지 하려면 다음 설정 중 하나를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="ae4fe-115">**Office 클라이언트에 대 한 안전 문서 설정 (파일은 심층 분석을 위해 Microsoft 클라우드로도 전송 됨)**</span><span class="sxs-lookup"><span data-stu-id="ae4fe-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="ae4fe-116">**안전한 보기를 통해 클릭할 수 있도록 허용 문서가 악성 파일인 것으로 식별**되는 경우에도이 옵션을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="ae4fe-117">작업을 마친 후 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-117">When you're finished, click **Save**.</span></span>

![ATP 안전한 첨부 파일 페이지](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="ae4fe-119">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell을 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="ae4fe-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ae4fe-120">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="ae4fe-121">_EnableSafeDocs_ 매개 변수는 전체 조직에 대 한 안전한 문서를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="ae4fe-122">문서가 악성으로 식별 된 경우에는 _AllowSafeDocsOpen_ 매개 변수를 사용 하 여 사용자가 문서를 여는 제한 된 보기를 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ae4fe-123">이 예에서는 전체 조직에 대해 안전한 문서를 사용 하도록 설정 하 고 제한 된 보기에서 악의적으로 식별 된 문서를 사용자가 열지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ae4fe-124">구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ae4fe-125">작동 여부는 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="ae4fe-125">How do I know this worked?</span></span>

<span data-ttu-id="ae4fe-126">안전한 문서를 사용 하도록 설정 하 고 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ae4fe-127">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동한 다음, **Office 응용 프로그램에서 제한 된 보기 외부에서 열 수 있는 파일을 신뢰 하는 경우 도움말 사용자의 안전한 상태 유지** 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="ae4fe-128">Exchange Online PowerShell에서 다음 명령을 실행 하 고 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4fe-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
