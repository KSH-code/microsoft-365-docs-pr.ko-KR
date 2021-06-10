---
title: Microsoft Defender for Endpoint(iOS용)에 대한 업데이트 배포
ms.reviewer: ''
description: 엔터프라이즈 환경에서 Linux에서 끝점용 Microsoft Defender 업데이트를 배포하는 방법에 대해 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 업데이트, 배포
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274727"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="a7e3d-104">Microsoft Defender for Endpoint(iOS용)에 대한 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="a7e3d-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a7e3d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a7e3d-105">**Applies to:**</span></span>
- [<span data-ttu-id="a7e3d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7e3d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7e3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7e3d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a7e3d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a7e3d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a7e3d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a7e3d-110">Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="a7e3d-111">Linux의 각 Endpoint용 Defender 버전에는 만료 날짜가 있습니다. 그 이후에는 더 이상 디바이스를 보호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="a7e3d-112">이 날짜 이전에 제품을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-112">You must update the product prior to this date.</span></span> <span data-ttu-id="a7e3d-113">만료 날짜를 확인하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="a7e3d-114">일반적으로 사용할 수 있는 끝점용 Microsoft Defender 기능은 배포에 사용되는 업데이트 채널(Beta(Insider), Preview(외부), 현재(프로덕션))에 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="a7e3d-115">Linux에서 Endpoint용 Defender를 수동으로 업데이트하려면 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e3d-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="a7e3d-116">RHEL 및 변형(CentOS 및 Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="a7e3d-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="a7e3d-117">SLES 및 변형</span><span class="sxs-lookup"><span data-stu-id="a7e3d-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="a7e3d-118">Ubuntu 및 데비안 시스템</span><span class="sxs-lookup"><span data-stu-id="a7e3d-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
