---

copyright:
  years: 2014, 2018
lastupdated: "2018-10-15"

---
{:new_window: target="_blank"}

# Novos locais e recursos do {{site.data.keyword.filestorage_short}}

O {{site.data.keyword.BluSoftlayer_full}} está introduzindo uma nova versão do
{{site.data.keyword.filestorage_full}}. O novo armazenamento está disponível em data centers selecionados é suportado pelo armazenamento flash a níveis de IOPS mais altos com criptografia para dados em repouso no nível de disco. Todo o armazenamento pedido nos data centers selecionados são criados automaticamente com a nova versão do {{site.data.keyword.filestorage_short}}.

**Nota:** o ponto de montagem do NFS para novos volumes mudou. Veja a seção **Novo ponto de montagem para volumes aprimorados do {{site.data.keyword.filestorage_short}}** para obter detalhes.

O novo {{site.data.keyword.filestorage_short}} está disponível nas regiões/data centers a seguir com mais disponibilidade do data center incluída em breve.

<table role="presentation">
  <tr>
    <td><strong>EUA 2</strong></td>
    <td><strong>União Europeia (UE)</strong></td>
    <td><strong>Austrália</strong></td>
    <td><strong>Canadá</strong></td>
    <td><strong>América Latina</strong></td>
    <td><strong>Ásia-Pacífico</strong></td>
  </tr>
  <tr>
    <td>DAL09<br />
	DAL10<br />
	DAL12<br />
	DAL13<br />
	SJC03<br />
        SJC04<br />
	WDC04<br />
	WDC06<br />
	WDC07<br />
	<br /><br /><br />
    </td>
    <td>AMS01<br />
        AMS03<br />
	FRA02<br />
	FRA04<br />
	FRA05<br />
	LON02<br />
	LON04<br />
	LON05<br />
	LON06<br />
	MIL01<br />
	OSLO1<br />
	PAR01<br />
    </td>
    <td>MEL01<br />
        SYD01<br />
        SYD04<br />
	<br /><br /><br /><br /><br /><br /><br /><br /><br />
    </td>
    <td>MON01<br />
        TOR01<br />
	<br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
    </td>
    <td>MEX01<br />
        SAO01<br />
	<br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
    </td>
    <td>CHE01<br />
        HKG02<br />
	SEO01<br />
	SNG01<br />
        TOK02<br />
	TOK04<br />
	TOK05<br />
	<br /><br /><br /><br /><br />
    </td>
  </tr>
</table>

*A Tabela 1 mostra nossa Disponibilidade do Data center. Cada região possui sua própria coluna. Algumas cidades, como Dallas, São José, Washington DC, Amsterdã, Frankfurt, Londres e Sydney, têm múltiplos data centers.*

O novo armazenamento tem os seguintes recursos e capacidades:

- [Criptografia gerenciada por provedor para dados em repouso](block-file-storage-encryption-rest.html). <br/> Todos os volumes {{site.data.keyword.filestorage_short}} são provisionados automaticamente como criptografados sem encargo adicional.
- 10 IOPS por opção de camada GB. <br/> Uma nova camada foi incluída no {{site.data.keyword.filestorage_short}} de tipo Endurance para suportar as cargas de trabalho de maior demanda.
- Armazenamento suportado todo em flash. <br/> O {{site.data.keyword.filestorage_short}} que é provisionado com as opções Endurance ou Performance em 2 IOPS por GB ou superior é suportado por armazenamento totalmente em flash.
- Suporte de Captura instantânea e Replicação.
- Opção de faturamento por hora incluído para armazenamento que é planejado para ser usado por menos de um mês integral.
- Até 48.000 IOPS para o {{site.data.keyword.filestorage_short}} provisionado com o tipo Performance.
- As taxas de IOPS são ajustáveis para melhorar o desempenho de mudanças sazonais de carga. Leia mais sobre esse recurso [aqui](adjustable-iops.html).
- Crie um clone de seus dados com o [recurso de Duplicação de volume do {{site.data.keyword.filestorage_short}}](how-to-create-duplicate-volume.html).
- O armazenamento é expansível em incrementos de GB até 12 TB imediatamente, sem a necessidade de criar uma duplicata ou de mover manualmente os dados para um volume maior. Leia mais sobre esse recurso [aqui](expandable_file_storage.html).

## Novo Ponto de Montagem para volumes  {{site.data.keyword.filestorage_short}}  aprimorados

Todos os volumes aprimorados do {{site.data.keyword.filestorage_short}} provisionados nesses data centers têm um ponto de montagem diferente de volumes não criptografados. Para assegurar-se de que esteja usando o ponto de montagem correto para seus volumes de armazenamento, é possível visualizar as informações de ponto de montagem na página **Detalhes do volume** na IU. Também é possível acessar o ponto de montagem correto por meio de uma chamada API: `SoftLayer_Network_Storage::getNetworkMountAddress()`.

Consulte esta página novamente para ver quando mais data centers serão submetidos a upgrade e os novos recursos e capacidades que estão sendo incluídos no {{site.data.keyword.filestorage_short}}.
