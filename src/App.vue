<script setup lang="ts">
import { fileTypeFromBlob } from 'file-type/browser';
// import * as FileType from 'file-type/browser';

const handleFiles = async (files: FileList) => {
  try {
    const file = files[0];
    console.log(file);

    // TODO
    // const typeFile = await fileTypeFromBlob(file.slice(0, 4100));
    // const typeFile = await FileType.fileTypeFromBlob(file.slice(0, 4100));
    // console.log(typeFile);

  } catch (error: any) {
    console.error(error);
  }
};

function onChange(e: Event): void {
  const target = e.target as HTMLInputElement;
  const { files } = target;
  if (!files) return;
  handleFiles(files);
}
</script>

<template>
  <input type="file" @change="onChange" />
</template>
