---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: a0e2ac250da3837b41134d3a04a21579a2fe923a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569038"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>構文  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>メソッド  
 MsmqBindingElementBase クラスは、メソッドを一切定義しません。  
  
## <a name="properties"></a>プロパティ  
 MsmqBindingElementBase クラスには、次のプロパティがあります。  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  
 データ型: string  
  
 アクセスの種類:読み取り専用  
  
 アプリケーションごとの配信不能キューの場所が含まれている URI です。ここには、期限切れのメッセージや、転送または配信に失敗したメッセージが配置されます。  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 データ型: string  
  
 アクセスの種類:読み取り専用  
  
 使用する配信不能キューの型を示す列挙型の値です。  
  
### <a name="durable"></a>Durable  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 このバインディングによって処理されるメッセージが永続的なものか不安定なものかを示す値です。  
  
### <a name="exactlyonce"></a>ExactlyOnce  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 このバインディングで処理されるメッセージが正確に 1 回だけ受信されるかどうかを示すブール値です。  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 データ型 : sint32  
  
 アクセスの種類:読み取り専用  
  
 受信アプリケーションにメッセージを配信する再試行サイクルの最大数です。  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  
 データ型: string  
  
 アクセスの種類:読み取り専用  
  
 有害メッセージの処理の設定です。  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 データ型 : sint32  
  
 アクセスの種類:読み取り専用  
  
 アプリケーション キューから読み取られるメッセージの即時再試行の最大回数です。  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 データ型 : datetime  
  
 アクセスの種類:読み取り専用  
  
 すぐに配信できなかったメッセージを配信しようとするときの、再試行サイクルの時間遅延を示す値です。  
  
### <a name="timetolive"></a>TimeToLive  
 データ型 : datetime  
  
 アクセスの種類:読み取り専用  
  
 このバインディングで処理されるメッセージの期限が切れるまで、メッセージをキュー内で保持する時間です。  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 このバインディングにより処理されるメッセージをトレースするかどうかを示すブール値です。  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 データ型 : boolean  
  
 アクセスの種類:読み取り専用  
  
 このバインディングにより処理されるメッセージのコピーをソース ジャーナル キューに保存するかどうかを示すブール値です。  
  
## <a name="requirements"></a>必要条件  
  
|MOF|Servicemodel.mof にて宣言済み。|  
|---------|-----------------------------------|  
|Namespace|root\ServiceModel で定義|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
