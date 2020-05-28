---
title: 장치 목록 CSV-파일
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: AutoPilot 용 CSV 파일을 Microsoft 365에서 비즈니스용으로 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399365"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="18f1e-103">장치 목록 CSV-파일</span><span class="sxs-lookup"><span data-stu-id="18f1e-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="18f1e-104">장치 목록 .csv 파일 형식</span><span class="sxs-lookup"><span data-stu-id="18f1e-104">Device list .csv file format</span></span>

<span data-ttu-id="18f1e-105">Windows Autopilot를 통해 장치를 관리 하 고 배포 하려면 장치에 대 한 특정 정보가 포함 된 .csv 파일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f1e-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="18f1e-106">장치 목록 파일의 열에는 지정 된 순서 대로 다음과 같은 헤더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f1e-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="18f1e-107">A 열: 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="18f1e-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="18f1e-108">B 열: 비워 둠</span><span class="sxs-lookup"><span data-stu-id="18f1e-108">Column B: leave blank</span></span>

- <span data-ttu-id="18f1e-109">C 열: 하드웨어 해시</span><span class="sxs-lookup"><span data-stu-id="18f1e-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="18f1e-110">하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f1e-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="18f1e-111">장치를 추가할 때는 프로필에도 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f1e-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="18f1e-112">프로필은 AutoPilot 배포 프로필을 장치 또는 장치 그룹에 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f1e-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="18f1e-113">관련 문서</span><span class="sxs-lookup"><span data-stu-id="18f1e-113">Related articles</span></span>

[<span data-ttu-id="18f1e-114">비즈니스 설명서 및 리소스에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18f1e-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="18f1e-115">Microsoft 365 for business 시작</span><span class="sxs-lookup"><span data-stu-id="18f1e-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="18f1e-116">비즈니스에 대 한 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="18f1e-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
