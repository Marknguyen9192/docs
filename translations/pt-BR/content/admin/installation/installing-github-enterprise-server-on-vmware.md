---
title: Instalar o GitHub Enterprise Server no VMware
intro: 'Para instalar o {{ site.data.variables.product.prodname_ghe_server }} no VMware, você deve fazer o download do cliente do VMware vSphere e, em seguida, fazer o download e implantar o software do {{ site.data.variables.product.prodname_ghe_server }}.'
redirect_from:
  - /enterprise/admin/articles/getting-started-with-vmware/
  - /enterprise/admin/articles/installing-vmware-tools/
  - /enterprise/admin/articles/vmware-esxi-virtual-machine-maximums/
  - /enterprise/admin/guides/installation/installing-github-enterprise-on-vmware/
  - /enterprise/admin/installation/installing-github-enterprise-server-on-vmware
versions:
  enterprise-server: '*'
---

### Pré-requisitos

- {{ site.data.reusables.enterprise_installation.software-license }}
- Você deve ter um Hypervisor VMware vSphere ESXi aplicado a uma máquina bare metal que vai executar a {{ site.data.variables.product.product_location_enterprise }}. As versões 5.5 a 6.7 são compatíveis. O Hpervisor ESXi é grátis e não inclui o Servidor vCenter (opcional). Para obter mais informações, consulte a [documentação do VMware ESXi](https://www.vmware.com/products/esxi-and-esx.html).
- Você precisará de acesso a um cliente vSphere. Se tiver o servidor vCenter, você poderá usar o cliente vSphere Web. Para obter mais informações, consulte "[Fazer login no servidor vCenter pelo cliente web vSphere](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.install.doc/GUID-CE128B59-E236-45FF-9976-D134DADC8178.html)" no guia da VMware.

### Considerações de hardware

{{ site.data.reusables.enterprise_installation.hardware-considerations-all-platforms }}

### Baixar a imagem do {{ site.data.variables.product.prodname_ghe_server }}

{{ site.data.reusables.enterprise_installation.enterprise-download-procedural }}
{{ site.data.reusables.enterprise_installation.download-license }}
{{ site.data.reusables.enterprise_installation.download-appliance }}
4. Selecione {{ site.data.variables.product.prodname_dotcom }} On-premises e clique em **VMware ESXi/vSphere (OVA)**.
5. Clique em **Download for VMware ESXi/vSphere (OVA)** (Baixar para VMware ESXi/vSphere [OVA]).

### Criar a instância do {{ site.data.variables.product.prodname_ghe_server }}

{{ site.data.reusables.enterprise_installation.create-ghe-instance }}

1. Usando o cliente vSphere Windows ou vCenter Web, importe a imagem do {{ site.data.variables.product.prodname_ghe_server }} que você baixou. Para ver as instruções, consulte "[Implantar modelo OVF ou OVA](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-17BEDA21-43F6-41F4-8FB2-E01D275FE9B4.html)" no guia da VMware.
    - Ao selecionar um armazenamento de dados, escolha um que tenha espaço suficiente para hospedar os discos da VM. Para as especificações mínimas de hardware recomendadas para o tamanho da sua instância, consulte "[Considerações de hardware](#hardware-considerations)". Recomendamos um provisionamento robusto com lazy zeroing.
    - Desmarque a caixa **Power on after deployment** (Ligar após a implantação), pois você terá que adicionar um volume de armazenamento anexado aos dados do repositório após o provisionamento da VM.
{{ site.data.reusables.enterprise_installation.create-attached-storage-volume }} Para obter instruções, consulte "[Adicionar novo disco rígido a uma máquina virtual](https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-F4917C61-3D24-4DB9-B347-B5722A84368C.html)" no guia da VMware.

### Configurar a instância do {{ site.data.variables.product.prodname_ghe_server }}

{{ site.data.reusables.enterprise_installation.copy-the-vm-public-dns-name }}
{{ site.data.reusables.enterprise_installation.upload-a-license-file }}
{{ site.data.reusables.enterprise_installation.save-settings-in-web-based-mgmt-console }} Para obter mais informações, consulte "[Configurar o appliance do {{ site.data.variables.product.prodname_ghe_server }}](/enterprise/admin/guides/installation/configuring-the-github-enterprise-server-appliance)".
{{ site.data.reusables.enterprise_installation.instance-will-restart-automatically }}
{{ site.data.reusables.enterprise_installation.visit-your-instance }}

### Leia mais

 - [Visão geral do sistema](/enterprise/admin/guides/installation/system-overview)