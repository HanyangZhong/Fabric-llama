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

// 表格数据
const table3Data = [
  {
    model: "Llama3.2-Vision-90B",
    original_acc: 49.8,
    original_sk: 2.5,
    finer_acc: 39.7,
    finer_sk: 12.8,
  },
  {
    model: "Llama3.2-Vision-90B + D-SFT",
    original_acc: 93,
    original_sk: 1,
    finer_acc: 51.7,
    finer_sk: 55.5,
  },
  {
    model: "Fabric-Llama-90B",
    original_acc: 94,
    original_sk: 0,
    finer_acc: 52.2,
    finer_sk: 54.5,
  },
]


const table4Data = [
  {
    domain: "Apparel",
    scenario: "Athletic wear for flexibility",
    key_properties: "Elasticity (E) Softness (S)",
    fabric_acc: "100%",
    fabric_selection: true,
    gpt_acc: "33.3%",
    gpt_selection: false,
    llama_acc: "50%",
    llama_selection: true,
  },
  {
    domain: "Apparel",
    scenario: "Summer dresses for children",
    key_properties: "Softness (S) Elasticity (E)",
    fabric_acc: "83.3%",
    fabric_selection: true,
    gpt_acc: "20%",
    gpt_selection: true,
    llama_acc: "0%",
    llama_selection: false,
  },
  {
    domain: "Home Textiles",
    scenario: "Light draping fabric for home decor",
    key_properties: "Thickness (t) Softness (S)",
    fabric_acc: "66.7%",
    fabric_selection: true,
    gpt_acc: "20%",
    gpt_selection: false,
    llama_acc: "50%",
    llama_selection: false,
  },
  {
    domain: "Home Textiles",
    scenario: "Durable fabric for frequent-use furniture",
    key_properties: "Texture (X) Thickness (t)",
    fabric_acc: "62.5%",
    fabric_selection: true,
    gpt_acc: "28.5%",
    gpt_selection: false,
    llama_acc: "62.5%",
    llama_selection: false,
  },
  {
    domain: "Workwear & Industrial Fabrics",
    scenario: "Protective fabric for work environments",
    key_properties: "Thickness (t) Elasticity (e-)",
    fabric_acc: "50%",
    fabric_selection: true,
    gpt_acc: "50%",
    gpt_selection: false,
    llama_acc: "50%",
    llama_selection: false,
  },
  {
    domain: "Workwear & Industrial Fabrics",
    scenario: "Heavy-duty material for robust applications",
    key_properties: "Texture (X) Thickness (T)",
    fabric_acc: "75%",
    fabric_selection: true,
    gpt_acc: "33.3%",
    gpt_selection: false,
    llama_acc: "25%",
    llama_selection: false,
  },
  {
    domain: "Outdoor & Functional Fabrics",
    scenario: "soft lining fabric for formal suits",
    key_properties: "Thickness (t-) Softness (S) Texture (x-)",
    fabric_acc: "80%",
    fabric_selection: false,
    gpt_acc: "42.8%",
    gpt_selection: false,
    llama_acc: "30%",
    llama_selection: false,
  },
  {
    domain: "Outdoor & Functional Fabrics",
    scenario: "Lightweight smooth fabric for formal shirts",
    key_properties: "Thickness (t-) Softness (S) Texture (x-)",
    fabric_acc: "90%",
    fabric_selection: true,
    gpt_acc: "45%",
    gpt_selection: false,
    llama_acc: "9.1%",
    llama_selection: false,
  },
  {
    domain: "Luxury & Specialty Fabrics",
    scenario: "Ultra-soft lightweight fabric for accessories",
    key_properties: "Softness (S) Thickness (t-)",
    fabric_acc: "50%",
    fabric_selection: true,
    gpt_acc: "50%",
    gpt_selection: false,
    llama_acc: "16.7%",
    llama_selection: false,
  },
  {
    domain: "Luxury & Specialty Fabrics",
    scenario: "Thick, luxurious fabric for premium interiors",
    key_properties: "Thickness (T) Elasticity (e-) Texture (X)",
    fabric_acc: "61.5%",
    fabric_selection: false,
    gpt_acc: "23%",
    gpt_selection: false,
    llama_acc: "15.3%",
    llama_selection: false,
  },
];

const getSelectionIcon = (selected) => (selected ? "✅" : "❌");
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
                    <el-tabs class="demo-tabs" model-value="Finetuning Experiment Results">

                    <!-- 第一个tab -->
                    <el-tab-pane label="Modality Experiment Results" name="Modality Experiment Results">

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

                    <el-tab-pane label="Finetuning Experiment Results" name="Finetuning Experiment Results">
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

                    <el-tab-pane label="Finer-grained Experiment Results" name="Finer-grained Experiment Results">
                        <el-table
                            :data="table3Data"
                            :default-sort="{ prop: 'finer_acc', order: 'descending' }"
                            scrollbar-always-on
                            style="width: 100%; table-layout: fixed;"
                        >
                            <!-- Model -->
                            <el-table-column prop="model" label="Model" width="330" sortable />
                            <!-- Original Test -->
                            
                            <el-table-column label="Original Test">
                            <el-table-column prop="original_acc" label="Overall ACC ↑" width="150" sortable />
                            <el-table-column prop="original_sk" label="Sk ↓" width="120" sortable />
                            </el-table-column>

                            <!-- Finer-grained Test -->
                            <el-table-column label="Finer-grained Test">
                            <el-table-column prop="finer_acc" label="Overall ACC ↑" width="150" sortable />
                            <el-table-column prop="finer_sk" label="Sk ↓" width="120" sortable />
                            </el-table-column>
                        </el-table>
                    </el-tab-pane>

                    <el-tab-pane label="Fabric Selection Experiment Results" name="Fabric Selection Experiment Results">
                        <el-table
                            :data="table4Data"
                            :default-sort="{ prop: 'fabric_acc', order: 'descending' }"
                            scrollbar-always-on
                            style="width: 100%; table-layout: fixed;"
                        >
                            <!-- 第一列：Domain -->
                            <el-table-column prop="domain" label="Domain" width="150" />

                            <!-- 第二列：Scenario -->
                            <el-table-column prop="scenario" label="Scenario" width="300" />

                            <!-- 第三列：Key Sorting Properties -->
                            <el-table-column prop="key_properties" label="Key Sorting Properties" width="250" />

                            <!-- Fabric-Llama-90B -->
                            <el-table-column label="Fabric-Llama-90B">
                                <el-table-column prop="fabric_acc" label="Sorting Acc ↑" width="100" />
                                <el-table-column label="Selection" width="100">
                                <template #default="scope">
                                    {{ getSelectionIcon(scope.row.fabric_selection) }}
                                </template>
                                </el-table-column>
                            </el-table-column>

                            <!-- GPT-4o -->
                            <el-table-column label="GPT-4o">
                                <el-table-column prop="gpt_acc" label="Sorting Acc ↑" width="100" />
                                <el-table-column label="Selection" width="100">
                                <template #default="scope">
                                    {{ getSelectionIcon(scope.row.gpt_selection) }}
                                </template>
                                </el-table-column>
                            </el-table-column>

                            <!-- Llama-Vision-90B -->
                            <el-table-column label="Llama-Vision-90B">
                                <el-table-column prop="llama_acc" label="Sorting Acc ↑" width="100" />
                                <el-table-column label="Selection" width="100">
                                <template #default="scope">
                                    {{ getSelectionIcon(scope.row.llama_selection) }}
                                </template>
                                </el-table-column>
                            </el-table-column>
                            </el-table>
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
  