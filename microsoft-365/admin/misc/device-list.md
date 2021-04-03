---
title: 장치 목록 CSV-file
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 비즈니스용 Microsoft 365에서 AutoPilot용 CSV 파일을 만드는 방법을 학습합니다.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579221"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="fce03-103">장치 목록 CSV-file</span><span class="sxs-lookup"><span data-stu-id="fce03-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="fce03-104">장치 목록 .csv 파일 형식</span><span class="sxs-lookup"><span data-stu-id="fce03-104">Device list .csv file format</span></span>

<span data-ttu-id="fce03-105">Windows Autopilot을 통해 장치를 관리하고 배포하려면 장치에 대한 특정 정보가 포함된 .csv 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fce03-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="fce03-106">장치 목록 파일의 열에는 지정된 순서대로 다음 헤더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce03-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="fce03-107">A 열: 장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="fce03-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="fce03-108">B 열: 비워 두기</span><span class="sxs-lookup"><span data-stu-id="fce03-108">Column B: leave blank</span></span>

- <span data-ttu-id="fce03-109">C 열: 하드웨어 해시</span><span class="sxs-lookup"><span data-stu-id="fce03-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="fce03-110">하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce03-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="fce03-111">디바이스를 추가할 때 프로필에도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce03-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="fce03-112">프로필은 장치 또는 장치 그룹에 AutoPilot 배포 프로필을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fce03-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="fce03-113">관련 문서</span><span class="sxs-lookup"><span data-stu-id="fce03-113">Related articles</span></span>

[<span data-ttu-id="fce03-114">비즈니스용 Microsoft 365 설명서 및 리소스</span><span class="sxs-lookup"><span data-stu-id="fce03-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="fce03-115">비즈니스용 Microsoft 365 시작</span><span class="sxs-lookup"><span data-stu-id="fce03-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="fce03-116">비즈니스용 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="fce03-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
