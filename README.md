# learn-implement-message-workflows-with-service-bus

https://docs.microsoft.com/ja-jp/learn/modules/implement-message-workflows-with-service-bus/

## 特記事項

VisualStudio 2019 で動作確認をするためのプロジェクトです。  
（接続文字列以外は実装済みです。）  
Microsoft.Azure.ServiceBus の Nuget は 3.1.0 から 4.1.3 に上げています、動作確認済みです。  


## Azure CLI 

[Azure CLI のインストール Microsoft Docs](https://docs.microsoft.com/ja-jp/cli/azure/install-azure-cli?view=azure-cli-latest)


Azure にログインする：

```powershell
az login
```


作成したサービスバスの接続文字列を取得する：  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus namespace authorization-rule keys list `
    --resource-group <your-resource-group>`
    --name RootManageSharedAccessKey `
    --query primaryConnectionString `
    --output tsv `
    --namespace-name <your-servicebus-namespace-name>

```

サービスバスのキューのメッセージ数を取得する：  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus queue show `
    --resource-group <your-resource-group> `
    --name salesmessages `
    --query messageCount `
    --namespace-name <your-servicebus-namespace-name> `
```

サービスバスのトピックとサブスクリプションのメッセージ数を取得する：  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus topic subscription show `
    --resource-group <your-resource-group>  `
    --namespace-name <your-servicebus-namespace-name> `
    --topic-name salesperformancemessages `
    --name EuropeAndAfrica  `
    --query messageCount
```

