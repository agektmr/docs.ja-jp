---
title: <diagnostics> アクティブ化
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: ac235b9a3c125cd3fe63ccd899e2ff92d4d3f31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278453"
---
# <a name="diagnostics-for-activation"></a>\<診断 > アクティブ化
Windows Communication Foundation (WCF) リスナーの診断機能を構成します。  
  
 \<system.serviceModel.activation>  
\<diagnostics>  
  
## <a name="syntax"></a>構文  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>型  
 `Type`  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`performanceCountersEnabled`|診断用パフォーマンス カウンターが有効であるかどうかを示すブール値。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<system.serviceModel.activation >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|リスナー プロセス SMSvcHost.exe の設定が含まれています。|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
