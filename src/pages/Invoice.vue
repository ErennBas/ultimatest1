<template>
	<div class="layout-invoice-page">
    <Button type="button" label="Print" icon="pi pi-print" @click="printClick" class="p-mb-3"></button>

    <div class="p-grid layout-invoice-content">
        <div class="p-col-12">
            <div class="card">
                <div class="p-d-flex p-jc-between">
                    <h5>INVOICE</h5>
                    <div class="p-d-flex p-flex-column p-ai-end">
                        <img src="assets/layout/images/extensions/prime-logo.svg" alt="invoice-logo"/>
                        <p class="p-mt-1">9137 3rd Lane California City, CA 93504.</p>
                    </div>
                </div>

                <div class="p-p-3">
					<DataTable :value="billData" class="p-invoice-datatable-responsive p-pb-3">
						<Column v-for="col of billCols" :field="col.field" :header="col.header" :key="col.field"></Column>
					</DataTable>

					<DataTable :value="productData" class="p-invoice-datatable-responsive p-datatable-sm p-py-6">
						<Column v-for="col of productCols" :field="col.field" :header="col.header" :key="col.field"></Column>
					</DataTable>

                    <div class="p-grid">
                        <div class="p-col-12 p-md-6">
                            <Panel header="BANK">
                                <div class="p-d-flex p-ai-center p-jc-between p-py-2">
                                    <span>Bank</span>
                                    <span class="p-text-bold">BestBank</span>
                                </div>
                                <div class="p-d-flex p-ai-center p-jc-between p-pt-2 p-py-2">
                                    <span>ACCOUNT BENEFICIARY</span>
                                    <span class="p-text-bold">Edward Williams</span>
                                </div>
                                <div class="p-d-flex p-ai-center p-jc-between p-pt-2 p-py-2">
                                    <span>SWIFT</span>
                                    <span class="p-text-bold">PJNWBXND</span>
                                </div>
                                <div class="p-d-flex p-ai-center p-jc-between p-pt-2 p-py-2">
                                    <span>IBAN</span>
                                    <span class="p-text-bold">GB04420235692263866724650931</span>
                                </div>
                            </Panel>
                        </div>
                        <div class="p-col-12 p-md-6">
                            <Panel header="TOTAL">
                                <div class="p-grid p-text-right">
                                    <div class="p-col-10">
                                        SUBTOTAL
                                    </div>
                                    <div class="p-col-2">
                                        <span class="pink-color">$1304.00</span>
                                    </div>

                                    <div class="p-col-10">
                                        <span>VAT</span>
                                    </div>
                                    <div class="p-col-2">
                                        <span class="pink-color">$234.72</span>
                                    </div>

                                    <div class="p-col-10">
                                        <span>TOTAL</span>
                                    </div>
                                    <div class="p-col-2">
                                        <span class="pink-color">$1538.72</span>
                                    </div>
                                </div>
                            </Panel>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

</template>

<script>
export default {
	data() {
		return {
			billData: [
				{
					'billTo': 'TOYOKSU SYSCOM CORPORATION 11-27, MEIEKI 4-CHROME NAKAMURA-KU, NAGOYA 450-0002 JAPAN',
					'date': '30/08/2021',
					'no': 'A/3100',
					'notes': 'N/A'
				}
			],

			billCols: [
				{ field: 'billTo', header: 'BILL TO' },
				{ field: 'date', header: 'DATE' },
				{ field: 'no', header: 'INVOICE NO' },
				{ field: 'notes', header: 'NOTES' }
			],

			productData: [
				{
					'description': 'License A',
					'quantity': '4',
					'price': '$99.00',
					'total': '$396.00'
				},
				{
					'description': 'License B',
					'quantity': '1',
					'price': '$790.00',
					'total': '$790.00'
				},
				{
					'description': 'License C',
					'quantity': '2',
					'price': '$59.00',
					'total': '$118.00'
				}
			],

			productCols: [
				{ field: 'description', header: 'DESCRIPTION' },
				{ field: 'quantity', header: 'QUANTITY' },
				{ field: 'price', header: 'UNIT PRICE' },
				{ field: 'total', header: 'LINE TOTAL' }
			]
		}
	},
	methods: {
		printClick() {
			window.print();
		}
	}
}
</script>

<style scoped>

</style>
