---
title: 모바일 장치 관리 인프라 종료 기준
description: Microsoft 365 Enterprise Microsoft Intune를 사용 하 여 모바일 장치 관리를 포함 합니다. 요구 사항 및 필수 구성 요소를 검토, Azure Active Directory 리소스를 사용 하 여 Intune 설정, iOS, macOS, Android, 및 Windows 등록 장치 앱을 배포, 구성 프로필 만들기, 규정 준수 정책 사용 및 모바일에 대 한 조건부 액세스를 사용 하도록 설정 Microsoft 365 엔터프라이즈와 장치 관리 합니다.
keywords: Microsoft 365, Microsoft 365 엔터프라이즈 모바일 장치 관리 Microsoft 365 Intune 설명서
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869890"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="6942b-105">모바일 장치 관리 인프라 종료 기준</span><span class="sxs-lookup"><span data-stu-id="6942b-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="6942b-106">*이 Microsoft 365 Enterprise의 E3 및 e 5 버전에 적용 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="6942b-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6942b-107">배포 프로세스의 다음 단계로 이동 하기 전에 구성 모바일 장치 관리 인프라에 대 한 다음과 같은 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="6942b-108">Intune이 설정되고 장치에 대한 조직 규칙을 적용할 Azure AD 사용자 및 그룹이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="6942b-109">사용자가 만든 정책을 장치가 수락할 수 있도록 Intune에서 장치를 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="6942b-110">사용자가 Exchange Online 및 SharePoint Online과 같은 조직의 Microsoft 365 클라우드 서비스에 액세스할 수 있도록 장치에 앱이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="6942b-111">사용자가 만든 Azure AD 사용자 및 그룹을 사용하여 바이러스 백신 사용 및 특정 앱 제한과 같은 기능이 구성되고 사용자 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="6942b-p102">장치의 방화벽 또는 암호 길이를 요구하는 준수 정책이 설정됩니다. 장치가 규정을 준수하지 못하면 조건부 액세스 권한이 조직 데이터에 대한 액세스를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="6942b-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6942b-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="6942b-115">Microsoft 365 enterprise-종단간 배포 프로세스의 다음 단계로 사용자 [정보 보호](infoprotect-infrastructure.md)하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942b-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
