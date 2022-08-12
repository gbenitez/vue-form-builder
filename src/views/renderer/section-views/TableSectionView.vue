<template>
    <div class="table-section">
      <div class="mt-md-5 font-2-vh-md mt-3-vh fw-bolder font-2-vh" v-show="section.isShowHeadline">
        <div :class="[section.headlineAdditionalClass, 'text-primary fw-normal']" v-text="section.headline"></div>
      </div>
      <div :class="[section.subHeadlineAdditionalClass, 'font-2-vh-md fw-light font-2-vh']" v-show="section.isShowHeadline" v-text="section.subHeadline">
      </div>
      <!--        <div class="headline-block p5" v-show="section.isShowHeadline">
            <h2 :class="section.headlineAdditionalClass" v-text="section.headline"></h2>
            <p :class="section.subHeadlineAdditionalClass" v-text="section.subHeadline"></p>
        </div>-->

        <div class="table-wrapper">
            <table :class="styles.TABLE.TABLE_CLASS">
                <!--- TODO: Sortable --->

                <TableRowView v-for="(rowId) in section.rows"
                              :key="rowId"
                              :section="section"
                              :row="rows[rowId]" />

                <tr>
                    <td colspan="2">
                        <AddRowControl @addRowNotify="addRow" />
                    </td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
    import {SECTION_VIEW_MIXINS} from "@/mixins/section-view-mixins";
    import {STYLE_INJECTION_MIXIN} from "@/mixins/style-injection-mixin";
    import AddRowControl from "@/views/builder/add-controls/AddRowControl";
    import TableRowView from "@/views/builder/row-views/TableRowView";

    export default {
        name: "TableSectionView",
        components: {TableRowView, AddRowControl},
        mixins: [SECTION_VIEW_MIXINS, STYLE_INJECTION_MIXIN],
        methods: {
        }
    }
</script>

<style scoped>

</style>
