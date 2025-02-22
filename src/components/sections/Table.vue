<script lang="ts" setup>

// 表格数据
const table1Data = [
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
    elasticity: 55,
    softness: 66,
    thickness: 89,
    texture: 82,
    overall: 73,
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
    sk: 16,
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
    elasticity: 9,
    softness: 26,
    thickness: 41,
    texture: 50,
    overall: 31.5,
    sk: 19.3,
  },
  {
    model: "Llama3.2-Vision-90B",
    modality: "Uncalibrated T-images + RGB",
    elasticity: 16,
    softness: 2,
    thickness: 31,
    texture: 29,
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
]

// 表格数据
const table2Data = [
  {
    model: "DeepSeek Janus-Pro-7B",
    elasticity: 28,
    softness: 41,
    thickness: 46,
    texture: 40,
    overall: 38.8,
    sk: 84.4,
  },
  {
    model: "DeepSeek Janus-Pro-7B + D-SFT",
    elasticity: 50,
    softness: 50,
    thickness: 50,
    texture: 50,
    overall: 50,
    sk: 100,
  },
  {
    model: "Llama3.2-Vision-11B",
    elasticity: 53,
    softness: 53,
    thickness: 46,
    texture: 44,
    overall: 49,
    sk: 60,
  },
  {
    model: "Llama3.2-Vision-11B + D-SFT",
    elasticity: 50,
    softness: 42,
    thickness: 51,
    texture: 45,
    overall: 47,
    sk: 31.4,
  },
  {
    model: "Llama3.2-Vision-90B",
    elasticity: 54,
    softness: 48,
    thickness: 48,
    texture: 49,
    overall: 49.8,
    sk: 2.5,
  },
  {
    model: "Llama3.2-Vision-90B + D-SFT",
    elasticity: 95,
    softness: 82,
    thickness: 100,
    texture: 95,
    overall: 93,
    sk: 1,
  },
  {
    model: "Fabric-Janus-7B",
    elasticity: 50,
    softness: 47,
    thickness: 50,
    texture: 50,
    overall: 47,
    sk: 5.5,
  },
  {
    model: "Fabric-Llama-11B",
    elasticity: 51,
    softness: 50,
    thickness: 59,
    texture: 52,
    overall: 53,
    sk: 33.1,
  },
  {
    model: "Fabric-Llama-90B",
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
                    <el-tabs class="demo-tabs" model-value="Method B">

                    <!-- 第一个tab -->
                    <el-tab-pane label="Method A" name="Modality Experiment Results">

                        <!-- 表格数据 -->
                        <el-table 
                            :data="table1Data"
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

                    <el-tab-pane label="Method B" name="Finetuning Experiment Results">
                        <!-- 表格数据 -->
                        <el-table 
                            :data="table2Data"
                            :default-sort="{ prop: 'overall', order: 'descending' }"
                            scrollbar-always-on
                            style="width: 100%"
                        >
                            <el-table-column prop="model" label="Model" width="180" sortable />
                            <el-table-column prop="elasticity" label="Elasticity ACC" min-width="120" sortable />
                            <el-table-column prop="softness" label="Softness ACC" min-width="120" sortable />
                            <el-table-column prop="thickness" label="Thickness ACC" min-width="120" sortable />
                            <el-table-column prop="texture" label="Texture ACC" min-width="120" sortable />
                            <el-table-column prop="overall" label="Overall ACC" min-width="120" sortable />
                            <el-table-column prop="sk" label="Sk ↓" min-width="100" sortable />
                        </el-table>
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
  