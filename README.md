# learn-implement-message-workflows-with-service-bus

https://docs.microsoft.com/ja-jp/learn/modules/implement-message-workflows-with-service-bus/

## ���L����

VisualStudio 2019 �œ���m�F�����邽�߂̃v���W�F�N�g�ł��B  
�i�ڑ�������ȊO�͎����ς݂ł��B�j  
Microsoft.Azure.ServiceBus �� Nuget �� 3.1.0 ���� 4.1.3 �ɏグ�Ă��܂��A����m�F�ς݂ł��B  


## Azure CLI 

[Azure CLI �̃C���X�g�[�� Microsoft Docs](https://docs.microsoft.com/ja-jp/cli/azure/install-azure-cli?view=azure-cli-latest)


Azure �Ƀ��O�C������F

```powershell
az login
```


�쐬�����T�[�r�X�o�X�̐ڑ���������擾����F  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus namespace authorization-rule keys list `
    --resource-group <your-resource-group>`
    --name RootManageSharedAccessKey `
    --query primaryConnectionString `
    --output tsv `
    --namespace-name <your-servicebus-namespace-name>

```

�T�[�r�X�o�X�̃L���[�̃��b�Z�[�W�����擾����F  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus queue show `
    --resource-group <your-resource-group> `
    --name salesmessages `
    --query messageCount `
    --namespace-name <your-servicebus-namespace-name> `
```

�T�[�r�X�o�X�̃g�s�b�N�ƃT�u�X�N���v�V�����̃��b�Z�[�W�����擾����F  

```powershell
PS learn-implement-message-workflows-with-service-bus> az servicebus topic subscription show `
    --resource-group <your-resource-group>  `
    --namespace-name <your-servicebus-namespace-name> `
    --topic-name salesperformancemessages `
    --name EuropeAndAfrica  `
    --query messageCount
```

