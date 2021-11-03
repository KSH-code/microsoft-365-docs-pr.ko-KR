---
title: SDK & 기본 API 테스트
description: SDK & 기본 API 테스트
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9e2c52d23c0e0c949059dc37eee4c1a59b35964e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704946"
---
# <a name="manage-your-resource-with-sdk--apis"></a>SDK API를 사용하여 리소스 & 관리
자동화는 자동화 및 DevOps 핵심적인 측면입니다. 리소스에 대한 테스트 기반을 관리하고 Microsoft 365 프로그래밍 방식의 테스트 결과를 얻은 다음 CI 도구와 통합할 계획입니까? 기본 API/SDK를 테스트하면 이러한 모든 API를 달성하는 데 도움이 될 수 있습니다. 

IT 전문가 및 앱 개발자는 이러한 API/SDK를 사용하여 다음을 할 수 있습니다. 
- 만들기, 업데이트 및 오프보드를 비롯한 테스트 기준 계정을 관리합니다. 
- 패키지 만들기, 업데이트, 삭제 및 다운로드를 포함하여 응용 프로그램 패키지를 관리합니다. 
- 테스트 요약, 자세한 테스트 결과 및 분석 결과를 얻습니다. 분석 결과에는 CPU 회귀 분석, CPU 사용률 분석, 메모리 회귀 분석 및 메모리 사용률 분석이 포함됩니다. 
- 테스트 결과를 다운로드하고 실행 비디오 녹화를 테스트합니다.  

아래 단계별 개요를 확인하여 Microsoft 365 서비스에 대한 테스트 베이스에서 이 새로운 기능에 액세스하는 Microsoft 365 알아보세요.

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>Python SDK를 사용하여 테스트 기본 계정 만들기의 단계별 예

1. 필수 구성 요소: 

- 필요한 구성 요소 아래에 설치합니다. 

    [구독이 없는](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) 경우 활성 구독이 있는 Azure 계정<br>
    [Python 2.7+ 또는 3.6+](https://www.python.org/downloads)<br>
    [CLI(Azure Command-Line 인터페이스)](/cli/azure/install-azure-cli) <br>

- 콘솔에서 pip 설치를 사용하여 라이브러리 패키지 설치 

```
pip install azure-identity 
pip install azure-mgmt-testbase  
```

- 개발 환경에서 인증 

코드를 로컬로 디버깅하고 실행할 때 개발자는 자신의 계정을 사용하여 Azure 서비스에 대한 호출을 인증하는 것이 일반적입니다. Azure-IDENTITY 패키지는 로컬 개발을 단순화하기 위해 Azure CLI를 통한 인증을 지원합니다. Azure CLI에 로그인하기 위해 를 ```az login ``` 실행합니다. 기본 웹 브라우저가 있는 시스템에서 Azure CLI는 브라우저를 시작하여 사용자를 인증합니다. 

Azure 서비스를 사용하여 Python 응용 프로그램을 인증하는 [방법을 | Microsoft Docs](/azure/developer/python/azure-sdk-authenticate)  및 기타 [https://pypi.org/project/azure-identity/](https://pypi.org/project/azure-identity/) 지원되는 인증 방법 

 - 다음 단계에서 사용할 원하는 이름으로 리소스 그룹을 만드세요. 

2. 아래 코드 코드는 다음을 포함하여 테스트 기본 계정을 만들기 위한 흐름을 설명합니다. 

- Azure와의 상호 작용을 위해 Azure CLI를 통해 자격 증명 요청 
- 이후 작업의 자격 증명 및 구독 ID로 테스트 기본 SDK 클라이언트 초기화 
- 기본 begin_create test_base_accounts 호출하여 테스트 기본 계정 만들기 

코드를 Python 개발 환경에 복사하고 "subscription-id"를 Azure 구독 ID 및 "resource-group-name"을 위에서 만든 리소스 그룹으로 대체합니다. 

 
```python

from azure.identity import AzureCliCredential
from azure.mgmt.testbase import TestBase
from azure.mgmt.testbase.models import TestBaseAccountResource
from azure.mgmt.testbase.models import TestBaseAccountSKU

# requesting token from Azure CLI for request
# For other authentication approaches, please see: https://pypi.org/project/azure-identity/
credential = AzureCliCredential()
subscription_id = "<subscription-id>"
resource_group = "<resource-group-name>"
testBaseAccount_name = "contoso-testbaseAccount"
testBaseAccount_location = "global"
sku_name = "S0"
sku_tier = "Standard"
sku_locations = {"global"}

# Create client
testBase_client = TestBase(credential, subscription_id)

# Create sku for test base account
sku = TestBaseAccountSKU(name=sku_name, tier=sku_tier, locations=sku_locations)

# Create test base account
parameters = TestBaseAccountResource(location=testBaseAccount_location, sku=sku)
testBaseAccount = testBase_client.test_base_accounts.begin_create(resource_group, testBaseAccount_name, parameters).result()
print("Create test base account:\n{}".format(testBaseAccount))

```


## <a name="learn-more"></a>자세히 알아보기 

SDK API에 대한 자세한 내용은 아래 링크를 & 참조하세요. 

**Azure 구독** 

- [활성 구독이 있는 Azure 계정](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) 

**Python SDK** 

- [테스트 기본 Python SDK 설명서](/python/api/overview/azure/mgmt-testbase-readme?view=azure-python-preview)
- [테스트 기본 Python SDK 샘플](https://aka.ms/testbase-sample-py) 
- [Python SDK의 Azure 일반 사용 패턴](/azure/developer/python/azure-sdk-overview#provision-and-manage-azure-resources-with-management-libraries) 

**REST API**  

- [REST API 설명서](https://aka.ms/testbase-api)  
