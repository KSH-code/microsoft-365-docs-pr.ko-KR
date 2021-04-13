---
title: Microsoft Defender 바이러스 백신 배포 및 사용
description: Microsoft Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, PowerShell cmdlet 또는 WMI를 통해 끝점 보호를 위해 Microsoft Defender 바이러스 백신을 배포합니다.
keywords: 배포, 사용, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: efc2aa0f48cb2bc55e729b65c892a07b74c1bc46
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691493"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="14986-104">Microsoft Defender 바이러스 백신 배포 및 사용</span><span class="sxs-lookup"><span data-stu-id="14986-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="14986-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="14986-105">**Applies to:**</span></span>

- <span data-ttu-id="14986-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="14986-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="14986-107">사용하는 관리 도구에 따라 Microsoft Defender 바이러스 백신 보호를 사용하도록 설정하거나 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14986-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="14986-108">Microsoft Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, Active Directory, Microsoft Azure, PowerShell cmdlet 및 WMI(Windows Management Instruction)를 사용하여 보호를 사용하도록 설정하는 방법에 대한 지침은 [Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md#ref2) 바이러스 백신 배포, 관리 및 보고의 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14986-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="14986-109">일부 시나리오에서는 VDI(가상 데스크톱 인프라) 환경과 같은 Microsoft Defender 바이러스 백신 보호를 성공적으로 배포하거나 구성하는 방법에 대한 추가 지침이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14986-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="14986-110">이 섹션의 나머지 문서에서는 VDI 또는 [RDS(원격](deployment-vdi-microsoft-defender-antivirus.md)데스크톱 서비스) 환경에서 VM(가상 컴퓨터)에 Microsoft Defender 바이러스 백신을 설정하는 데 대한 종단적인 조언과 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14986-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="14986-111">관련 문서</span><span class="sxs-lookup"><span data-stu-id="14986-111">Related articles</span></span>

- [<span data-ttu-id="14986-112">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="14986-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="14986-113">Microsoft Defender 바이러스 백신 배포, 업데이트 관리 및 보고</span><span class="sxs-lookup"><span data-stu-id="14986-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="14986-114">VDI(가상 데스크톱 인프라) 환경의 Microsoft Defender 바이러스 백신 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="14986-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)