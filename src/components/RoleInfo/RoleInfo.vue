<template>
  <v-sheet width="300" class="mx-auto">
    <v-form>
      <div class="text-subtitle-1 text-medium-emphasis">角色名称</div>
      <v-text-field
        v-model="firstName"
        :rules="rules"
        density="compact"
        placeholder="请输入角色名称"
        variant="outlined"
      ></v-text-field>
      <div class="text-subtitle-1 text-medium-emphasis">是否启动</div>
      <v-container fluid>
        <v-radio-group
          v-model="inline"
          inline
          :rules="[(v) => !!v || '请选择是否启动']"
        >
          <v-radio label="是" value="radio-1"></v-radio>
          <v-radio label="否" value="radio-2"></v-radio>
        </v-radio-group>
      </v-container>
      <div class="text-subtitle-1 text-medium-emphasis">备注</div>
      <v-textarea
        v-model="bio"
        auto-grow
        color="deep-purple"
        rows="2"
        variant="outlined"
      ></v-textarea>
      <v-btn type="submit" block class="mt-2">提交</v-btn>
    </v-form>
  </v-sheet>
</template>
<script>
export default {
  data() {
    return {
      inline: null,
      bio: null,
      firstName: "",
      rules: [
        (value) => {
          if (value) return true;
          return "请输入角色名称";
        },
      ],
    };
  },
};
</script>

<style>
</style>