<script lang="ts" setup>

// 表格数据
const tableData = [
  {
    model: "GPT-4o",
    modality: "RGB",
    elasticity: 54,
    softness: 61,
    thickness: 77,
    texture: 84,
    overall: 69,
    sk: 14.2,
  },
  {
    model: "GPT-4o",
    modality: "One Calibrated T-image + RGB",
    elasticity: 54,
    softness: 63,
    thickness: 89,
    texture: 85,
    overall: 72.7,
    sk: 12.5,
  },
  {
    model: "GPT-4o",
    modality: "Uncalibrated T-images + RGB",
    elasticity: 52,
    softness: 60,
    thickness: 82,
    texture: 73,
    overall: 69,
    sk: 10.7,
  },
  {
    model: "GPT-4o",
    modality: "Calibrated T-images + RGB",
    elasticity: 55,
    softness: 64,
    thickness: 95,
    texture: 90,
    overall: 76,
    sk: 1.6,
  },
  {
    model: "Llama3.2-Vision-90B",
    modality: "RGB",
    elasticity: 23,
    softness: 14,
    thickness: 41,
    texture: 33,
    overall: 27.7,
    sk: 41.8,
  },
  {
    model: "Llama3.2-Vision-90B",
    modality: "One Calibrated T-image + RGB",
    elasticity: 30,
    softness: 24,
    thickness: 43,
    texture: 29,
    overall: 31.5,
    sk: 19.3,
  },
  {
    model: "Llama3.2-Vision-90B",
    modality: "Uncalibrated T-images + RGB",
    elasticity: 16,
    softness: 22,
    thickness: 32,
    texture: 20,
    overall: 19.5,
    sk: 13.9,
  },
  {
    model: "Llama3.2-Vision-90B",
    modality: "Calibrated T-images + RGB",
    elasticity: 54,
    softness: 48,
    thickness: 48,
    texture: 49,
    overall: 49.8,
    sk: 2.5,
  },
  {
    model: "Fabric-Llama-90B",
    modality: "Calibrated T-images + RGB",
    elasticity: 90,
    softness: 89,
    thickness: 100,
    texture: 97,
    overall: 94,
    sk: 0,
  },
]
</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">More Results</h1>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

                <!-- 卡片 -->
                <el-card class="card">

                    <!-- 默认tab -->
                    <el-tabs class="demo-tabs" model-value="Method A">

                    <!-- 第一个tab -->
                    <el-tab-pane label="Method A" name="Method A">

                        <!-- 表格数据 -->
                        <el-table 
                            :data="tableData"
                            :default-sort="{ prop: 'overall', order: 'descending' }"
                            scrollbar-always-on
                            style="width: 100%"
                        >
                            <el-table-column prop="model" label="Model" width="180" sortable />
                            <el-table-column prop="modality" label="Modality Data" min-width="200" />
                            <el-table-column prop="elasticity" label="Elasticity ACC" min-width="120" sortable />
                            <el-table-column prop="softness" label="Softness ACC" min-width="120" sortable />
                            <el-table-column prop="thickness" label="Thickness ACC" min-width="120" sortable />
                            <el-table-column prop="texture" label="Texture ACC" min-width="120" sortable />
                            <el-table-column prop="overall" label="Overall ACC" min-width="120" sortable />
                            <el-table-column prop="sk" label="Sk ↓" min-width="100" sortable />
                        </el-table>
                    </el-tab-pane>

                    <el-tab-pane label="Method B" name="Method B">
                        Method B
                    </el-tab-pane>

                    <el-tab-pane label="Method C" name="Method C">
                        Method C
                    </el-tab-pane>

                    <el-tab-pane label="Method D" name="Method D">
                        Method D
                    </el-tab-pane>
                    </el-tabs>

                </el-card>
            </el-col>
        </el-row>

    </div>
</template>

<style scoped>
.card {
    margin-top: 20px;
}
</style>
  