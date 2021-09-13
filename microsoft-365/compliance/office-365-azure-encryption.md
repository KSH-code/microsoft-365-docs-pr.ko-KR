---
title: Azure의 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Azure 디스크 암호화와 같은 Azure에서 사용할 수 있는 암호화에 대해 자세히 알아보기
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216742"
---
# <a name="encryption-in-azure"></a>Azure의 암호화

암호화된 통신 및 운영 프로세스와 같은 Azure의 기술 보호책은 데이터를 안전하게 유지하는 데 도움이 됩니다. 또한 추가 암호화 기능을 구현하고 자체 암호화 키를 관리할 수 있습니다. 고객 구성에 관계없이 Microsoft는 Azure에서 고객 데이터를 보호하기 위해 암호화를 적용합니다. 또한 Microsoft는 암호화 키를 암호화, 제어 및 관리하고 데이터에 대한 액세스를 제어 및 감사하는 다양한 고급 기술을 통해 Azure에서 호스트되는 데이터를 제어할 수 있습니다. 또한 Azure Storage 보안 기능 집합을 제공하면 개발자가 보안 응용 프로그램을 빌드할 수 있습니다.

Azure는 한 위치에서 다른 위치로 이동할 때 데이터를 보호하기 위한 다양한 메커니즘을 제공합니다. Microsoft는 클라우드 서비스와 고객 간을 이동하는 경우 TLS를 사용하여 데이터를 보호합니다. Microsoft의 데이터 센터는 Azure 서비스에 연결하는 클라이언트 시스템과 TLS 연결을 협상합니다. PFS(Perfect Forward Secrecy)는 고객의 클라이언트 시스템과 Microsoft 클라우드 서비스 간의 연결을 고유한 키로 보호합니다. 또한 연결은 RSA 기반 2,048비트 암호화 키 길이를 사용합니다. 이 조합을 사용하면 다른 사용자가 전송 중인 데이터를 가로채고 액세스하기가 어렵습니다.

클라이언트 쪽 [암호화,](/azure/storage/storage-client-side-encryption)HTTPS 또는 SMB 3.0을 사용하여 응용 프로그램과 Azure 간에 전송되는 데이터를 보호할 수 있습니다. 자체 VM(가상 컴퓨터)과 사용자 간의 트래픽에 대해 암호화를 사용하도록 설정할 수 있습니다. [Azure Virtual Networks를](https://azure.microsoft.com/services/virtual-network/)사용하면 업계 표준 IPsec 프로토콜을 사용하여 회사 VPN 게이트웨이와 Azure 간의 트래픽과 가상 네트워크에 있는 VM 간의 트래픽을 암호화할 수 있습니다.

미사용 데이터의 경우 Azure는 AES-256 지원과 같은 다양한 암호화 옵션을 제공하여 요구에 가장 적합한 데이터 저장소 시나리오를 선택할 수 있는 유연성을 제공합니다. 서비스 암호화를 사용하여 Azure Storage 데이터를 Storage 데이터를 자동으로 암호화할 수 있으며, VM에서 사용하는 운영 [체제 및](/azure/storage/storage-service-encryption)데이터 디스크를 암호화할 수 있습니다. 자세한 내용은 Azure의 가상 [머신에 대한 Windows 권장 사항을 참조하세요.](/azure/security/azure-security-disk-encryption) 또한 공유 액세스 서명을 사용하여 Azure Storage 개체에 대한 [위임된 액세스 권한을 부여할 수 있습니다.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure는 또한 데이터 웨어하우스 및 데이터 웨어하우스에 투명한 데이터 암호화 암호화를 Azure SQL Database [제공합니다.](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Azure의 암호화에 대한 자세한 내용은 Azure 암호화 개요 및 [Azure](/azure/security/security-azure-encryption-overview) 데이터 암호화 미사용 을 [참조하세요.](/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Azure 디스크 암호화

Azure 디스크 암호화를 사용하면 IaaS(Windows Linux Infrastructure as a Service) VM 디스크를 암호화할 수 있습니다. Azure 디스크 암호화는 Windows 및 Linux의 DM-Crypt 기능을 활용하여 운영 체제 및 데이터 디스크에 볼륨 수준 암호화를 제공합니다. 또한 VM 디스크의 모든 데이터가 Azure 저장소에 보관된 경우 암호화됩니다. Azure 디스크 암호화는 Azure Key Vault와 통합되어 암호화 키와 암호의 사용을 제어, 관리 및 감사하는 데 도움이 됩니다.

자세한 내용은 Azure의 가상 [머신에 대한 Windows 권장 사항을 참조하세요.](/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Azure Storage 서비스 암호화

Azure Storage [암호화를](/azure/storage/storage-service-encryption)사용하는 경우 Azure Storage 저장하기 전에 데이터를 자동으로 암호화하고 검색하기 전에 데이터를 암호 해독합니다. 암호화, 암호 해독 및 키 관리 프로세스는 사용자에게 완전히 투명합니다. Azure Storage 서비스 암호화는 [Azure Blob](https://azure.microsoft.com/services/storage/blobs/) 및 Azure 파일에 Storage [수 있습니다.](https://azure.microsoft.com/services/storage/files/) 서비스 암호화와 함께 Microsoft에서 관리하는 암호화 Azure Storage 사용할 수도 있습니다. 또는 자체 암호화 키를 사용할 수도 있습니다. (자체 키를 사용하는 데 대한 자세한 내용은 Azure Storage 자격 증명 모음의 고객 관리 키를 사용하여 서비스 암호화를 [참조하세요.](/azure/storage/common/storage-service-encryption-customer-managed-keys) Microsoft 관리 키를 사용하는 데 대한 자세한 내용은 Storage 서비스 암호화 [for Data ()를 참조하세요.](/azure/storage/storage-service-encryption) 또한 암호화 사용을 자동화할 수 있습니다. 예를 들어 Azure Storage Resource [Provider REST API, Storage](/rest/api/storagerp/)Resource Provider Client Library for [.NET,](/dotnet/api/overview/azure/storage)Azure PowerShell 또는 [Azure CLI](/azure/storage/storage-azure-cli)를 사용하여 저장소 계정에서 Storage 서비스 암호화를 [프로그래밍식으로](/powershell/azureps-cmdlets-docs)사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

일부 Microsoft 365 서비스는 Azure를 사용하여 데이터를 저장합니다. 예를 들어 SharePoint 및 비즈니스용 OneDrive Azure Blob 저장소에 데이터를 저장하고, Microsoft Teams 서비스에 대한 데이터를 테이블, blob 및 큐에 저장합니다. 또한 Microsoft 365 규정 준수 센터 준수 관리자 기능은 암호화된 형태로 저장되는 고객이 입력한 데이터를 Azure Cosmos DB , PaaS(Platform as a [Service),](/azure/cosmos-db/database-encryption-at-rest)전역 분산 다중 모델 데이터베이스로 저장합니다. Azure Storage 서비스 암호화는 Azure Blob 저장소 및 테이블에 저장된 데이터를 암호화하며, Azure 디스크 암호화는 큐의 데이터를 암호화하고 Windows 및 IaaS 가상 컴퓨터 디스크를 암호화하여 운영 체제 및 데이터 디스크에 볼륨 암호화를 제공합니다. 이 솔루션은 가상 컴퓨터 디스크의 모든 데이터가 Azure 저장소에 보관된 동안 암호화되도록 합니다. [Azure Cosmos DB의](/azure/cosmos-db/database-encryption-at-rest) 미사용 암호화는 보안 키 저장소 시스템, 암호화된 네트워크 및 암호화 API를 비롯한 여러 보안 기술을 사용하여 구현됩니다.

## <a name="azure-key-vault"></a>Azure Key Vault

보안 키 관리는 암호화 모범 사례의 핵심이 아니며, 또한 클라우드에서 데이터를 보호하는 데도 중요합니다. [Azure Key Vault를](/azure/key-vault/key-vault-whatis) 사용하면 HSM(하드웨어 보안 모듈)에 저장된 키를 사용하는 암호와 같은 키와 작은 암호를 암호화할 수 있습니다. Azure Key Vault는 클라우드 서비스에서 사용하는 암호화 키에 대한 액세스를 관리하고 제어하기 위해 Microsoft에서 권장하는 솔루션입니다. 액세스 키에 대한 사용 권한을 서비스 또는 계정이 있는 Azure Active Directory 있습니다. Azure Key Vault는 HSM 및 키 관리 소프트웨어를 구성, 패치 및 유지 관리해야 하는 조직의 필요성을 완화합니다. Azure Key Vault를 사용하여 Microsoft는 키와 응용 프로그램에 직접 액세스할 수 없는 것을 볼 수 없습니다. 제어를 유지 관리해야 합니다. HSM에서 키를 가져오거나 생성할 수도 있습니다. Azure Information Protection을 포함하는 구독이 있는 조직은 고객 관리 키 BYOK(Bring [Your Own Key)를](/information-protection/plan-design/byok-price-restrictions) 사용하여 사용을 기록하도록 Azure Information Protection 테넌트를 구성할 수 [있습니다.](/information-protection/deploy-use/log-analyze-usage)