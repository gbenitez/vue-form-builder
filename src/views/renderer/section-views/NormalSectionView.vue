<template>
    <div class="normal-section">
      <div class="mt-md-5 font-2-vh-md mt-3-vh fw-bolder font-2-vh" v-if="section.isShowHeadline" v-show="section.isShowHeadline">
        <div :class="[section.headlineAdditionalClass, 'text-primary fw-normal']" v-text="section.headline"></div>
      </div>
      <div :class="[section.subHeadlineAdditionalClass, 'font-2-vh-md fw-light font-2-vh']" v-show="section.isShowHeadline" v-text="section.subHeadline">
      </div>
<!--        <div class="headline-block" v-show="section.isShowHeadline">
            <h2 :class="section.headlineAdditionalClass" v-text="section.headline"></h2>
            <p :class="section.subHeadlineAdditionalClass" v-text="section.subHeadline"></p>
        </div>-->

        <div :class="containerClasses">
            <ControlView
                v-for="controlId in section.controls"
                :key="controlId"
                :control="controls[controlId]"
                :parent-id="section.uniqueId"
                :value-container="valueContainer"
                :validation-errors="validationErrors"
                :read-only="readOnly"
            />
        </div>
    </div>
</template>

<script>
    import {RENDERER_SECTION_VIEW_MIXIN} from "@/mixins/renderer-section-view-mixin";

    /**
     * @property {Object} section
     * @property {Object} rows RowId - RowData
     * @property {Object} controls ControlId - ControlData
     * @property {Array} section.rows
     * @property {Array} section.controls
     */
    export default {
        name: "NormalSectionView",
        mixins: [RENDERER_SECTION_VIEW_MIXIN],
        data: () => ({

        }),

    }
</script>
