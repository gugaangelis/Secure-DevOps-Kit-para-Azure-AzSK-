
> O Secure DevOps Kit para Azure (AzSK) foi criado pela divisão Core Services Engineering & Operations (CSEO) da Microsoft para ajudar a acelerar a adoção do Azure pela TI da Microsoft. Compartilhamos o AzSK e sua documentação com a comunidade para fornecer orientações sobre como escanear, implantar e operacionalizar recursos na nuvem rapidamente, em todas as etapas do DevOps, mantendo o controle sobre segurança e governança.
<br>O AzSK não é um produto oficial da Microsoft – trata-se, na verdade, de uma tentativa de compartilhar as melhores práticas da Microsoft CSEO com a comunidade.
# Secure DevOps Kit para Azure (AzSK)

## Content
- [Overview](README.md#overview)  
- [Setting up `Secure DevOps Kit for Azure`](README.md#setting-up-secure-devops-kit-for-azure)
- [Getting started with `Secure DevOps Kit for Azure`](README.md#getting-started-with-secure-devops-kit-for-azure)
- [Complete feature set of `Secure DevOps Kit for Azure`](README.md#complete-feature-set-of-secure-devops-kit-for-azure)  
- [What do you want to use the secure devops kit for?](README.md#what-do-you-want-to-use-the-secure-devops-kit-for)  
- [References](README.md#references)  

----------------------------------------------
### Overview

O "Secure DevOps Kit for Azure" (doravante denominado 'AzSK') é uma coleção de scripts, ferramentas, extensões, automações, etc., que atende às necessidades de segurança de ponta a ponta da assinatura e dos recursos do Azure para equipes de DevOps, utilizando ampla automação e integrando a segurança aos fluxos de trabalho nativos de DevOps, ajudando a alcançar um DevOps seguro com foco nestas 6 áreas:

Proteger a assinatura: Uma assinatura de nuvem segura fornece uma base sólida sobre a qual as atividades subsequentes de desenvolvimento e implantação podem ser realizadas. Uma equipe de engenharia deve ter a capacidade de implantar e configurar a segurança na assinatura, incluindo elementos como alertas, políticas ARM, RBAC, políticas do Security Center, JEA, bloqueios de recursos, etc. Da mesma forma, deve ser possível verificar se todas as configurações estão em conformidade com uma linha de base segura.

Habilitar o desenvolvimento seguro: Durante as fases de codificação e desenvolvimento inicial, os desenvolvedores devem ter a capacidade de escrever código seguro e testar a configuração segura de seus aplicativos em nuvem. Assim como os testes de verificação de compilação (BVTs), introduzimos o conceito de testes de verificação de segurança (SVTs), que podem verificar a segurança de vários tipos de recursos no Azure.
Integre a segurança ao CI/CD: A automação de testes é um princípio fundamental do DevOps. Enfatizamos isso fornecendo a capacidade de executar SVTs como parte do pipeline CI/CD do VSTS. Esses SVTs podem ser usados ​​para garantir que a assinatura de destino usada para implantar um aplicativo na nuvem e os recursos do Azure nos quais o aplicativo é baseado estejam configurados de maneira segura.
Garantia Contínua: No ambiente DevOps em constante mudança, é importante abandonar a mentalidade de que a segurança é um marco. Precisamos tratar a segurança como um estado continuamente variável de um sistema. Isso é possível por meio de recursos que permitem a garantia contínua usando uma combinação de runbooks de automação, agendamentos etc.
Alertas e Monitoramento: A visibilidade do status de segurança é importante para equipes de aplicativos individuais e também para equipes corporativas centrais. Fornecemos soluções que atendem às necessidades de ambas. Além disso, a solução abrange todas as etapas do DevOps, efetivamente preenchendo a lacuna entre a equipe de desenvolvimento e a equipe de operações do ponto de vista da segurança, por meio das visões únicas e integradas que gera.
Governança de Riscos na Nuvem: Por fim, subjacente a todas as atividades do kit está uma estrutura de telemetria que gera eventos que capturam uso, adoção, resultados de avaliação etc. Isso nos permite fazer melhorias mensuráveis ​​na segurança, visando áreas de alto risco e uso máximo antes de outras. 

![Secure_DevOps_Kit_for_Azure](Images/Secure_DevOps_Kit_Azure.PNG)

[Back to top...](README.md#content)  

### Setting up Secure DevOps Kit for Azure
1. Você pode seguir o [installation guide](00a-Setup/Readme.md) e instale o AzSK em seu sistema.
2. Após a conclusão da instalação, certifique-se de estar conectado à sua assinatura do Azure no PowerShell ISE.

> Cabe aqui uma breve observação sobre o uso do PowerShell (e do PowerShell ISE). O AzSK utiliza amplamente funções e módulos baseados em PowerShell para realizar configurações de segurança, provisionamento e para executar verificações e testes de segurança. Alguns dos nossos usuários iniciantes do AzSK também têm um primeiro contato com o PowerShell/PowerShell ISE como parte da experiência de primeiro uso. Dado o quão amplamente o PowerShell é usado (e útil) em diversas atividades no Azure, recomendamos fortemente que você supere os desafios iniciais. Várias pessoas (incluindo alguns membros da nossa própria equipe) eram iniciantes no PowerShell até algumas semanas atrás. No entanto, depois de superarem as dificuldades iniciais, tudo correu bem.

Se você concluiu as etapas acima, está tudo pronto para começar a usar o AzSK.

[Back to top...](README.md#content)
### Primeiros passos com o Secure DevOps Kit para Azure

Para usuários iniciantes, recomendamos que leiam esta seção para se familiarizarem com o conjunto de ferramentas. A leitura do guia de primeiros passos não levará mais de 30 minutos. Depois disso, você poderá explorar os recursos individuais em detalhes na seção seguinte. [*Complete feature set of Secure DevOps Kit for Azure*](README.md#complete-feature-set-of-secure-devops-kit-for-azure).  

#### Os dois casos de uso básicos:

Regardless of your specific functional role, it is likely that you are concerned about two things when it comes to security in Azure. Click on the links below to walk through these 2 'kick start' use cases of AzSK.
1. [Security of your subscription](00b-Getting-Started/GettingStarted_SubscriptionSecurity.md)
2. [Security of various azure service instances used by your solution or application](00b-Getting-Started/GettingStarted_AzureServiceSecurity.md)  

These use cases will tell you which commands you will need to run, what would happen in the background and what will be the output that you will get.  

By leveraging the extensive degree of automation that AzSK has to offer, ability to centrally deploy and manage policies/rules and the uniform behavior of scripts across the kit, you can save several hours of what would otherwise be manual security checks and examination.  

As you get familiar with and begin to use the 'downstream' capabilities (CICD, Continuous Compliance, Log Analytics support, etc.), the power of security automation and the seamless end-to-end experience that the AzSK unleashes will become more evident.  

[Back to top...](README.md#content) 

### Complete feature set of Secure DevOps Kit for Azure

|Feature Area | Secure DevOps Kit Feature|
|-------------|--------------------------|
[Secure the subscription](01-Subscription-Security/Readme.md) | <ul><li>Subscription Health Check</li> <li>Subscription Provisioning<ul><li> Alerts Configuration</li><li>ARM Policy Configuration</li><li>Azure Security Center Configuration</li><li>Access control (IAM) Hygiene</li>  </ul> </li></ul>
[Enable secure development](02-Secure-Development/Readme.md) | <ul><li>Security Verification Tests (SVT) </li><li>Security IntelliSense- VS Extension </li></ul>
[Integrate security into CICD](03-Security-In-CICD/Readme.md) | <ul><li>AzSK VS Extension-executes SVTs in a CICD pipeline </li></ul>
[Continuous Assurance](04-Continous-Assurance/Readme.md) | <ul><li>Security scanning via Azure Automation Runbooks</li></ul>
[Alerting & Monitoring](05-Alerting-and-Monitoring/Readme.md) | <ul><li>Monitoring Solution for AzSK containing:<ul><li>Security dashboard views covering security state/actions</li><li>Alerts with pertinent search queries</li></ul></li></ul>
[Cloud Risk Governance](06-Security-Telemetry/Readme.md) | <ul><li>Control/usage telemetry through Insights</li></ul>

[Back to top...](README.md#content) 
### What do you want to use the secure devops kit for?
As you can see from the summary description above, the "Secure DevOps Kit for Azure" (we will call it AzSK to be brief hereafter), can be used by many different stakeholders. So depending on your role in the DevOps ecosystem, one or more of the below scenarios may apply to you. The skillset needed to use the capabilities of the kit and the prerequisites you need to have on your machine will vary based on your scenario. Here are a few sample stakeholders and some points about *how* they may try to use the AzSK:  

|Stakeholders / Persona   |Capabilities of the kit     |
| ---- | ---- |
|**Subscription Owners**| Check the overall security health of your Azure subscription.<br> Ensure that artifacts such as Alerts for important activities, ARM policy, resource locks, RBAC roles, etc. are properly provisioned. |
|**Development/Engineering**| Get inline support with security tips and corrections while writing code for Azure apps (and also standard web applications in general).<br>  Test that Azure resources you are using for your application/solutions are configured and deployed securely.<br> Enable security in CICD by including various security tests in the build/release pipelines|
|**Deployment Team**| Ensure that a solution being deployed to a target Azure environment has an assured level of security by controlling deployment workflows according to outcomes of security checks.|
|**Operations Team**| Observe the security progress and state of the Azure subscription and the applications running in the subscription. Track security state in a 'continuous' manner and ensure that there is no downward 'drift' from a secure state.<br>Get support for frequently missed operational security activities such as key rotation, access reviews, deprovisioning of privileged accounts, etc.|
|**Compliance Team**| Ensure that various, often challenging, compliance requirements (e.g., SOX) are met for Azure-based solutions.|
|**IT Security Teams**| Use all of the above depending on the InfoSec domain you are engaged in as a 'Security Analyst'.|

>  Note that, increasingly, in a DevOps culture, some of the roles listed in the left column above blend together. So, for instance, the same person who is writing code may also be involved in the CICD pipeline setup or the deployment stages of a solution. So please consider the roles above as functional responsibilities as opposed to hard segregations of stakeholders.

[Back to top...](README.md#content) 

### References
- AzSK Module <a href="https://www.powershellgallery.com/packages/AzSK/">@PSGallery</a>
- AzSK Security Controls Portal @https://aka.ms/azskosstcp
- Security IntelliSense <a href="https://marketplace.visualstudio.com/items?itemName=AzSDKTeam.SecurityIntelliSense-Preview">@VisualStudio Marketplace</a>
- Visual Studio Online CICD Build/Release Extension <a href="https://marketplace.visualstudio.com/items?itemName=azsdktm.AzSDK-task">@VisualStudio Marketplace</a>
- For any other issues or feedback please drop a mail to <a href="mailto:azsksup@microsoft.com">AzSK Support</a>
