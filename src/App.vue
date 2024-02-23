<template>
  <main class="w-full min-h-screen bg-slate-100">
    <div class="container px-4 pt-4 mx-auto">
      <div class="flex space-x-4">
        <!-- Buttons -->

        <div class="bg-white rounded-md w-fit">
          <h1 class="p-4 text-xl font-semibold">Buttons</h1>
          <hr />
          <div class="flex flex-col items-start p-4 space-y-2 buttons">
            <Button>Continue</Button>
            <Button variant="destructive">Destructive</Button>
            <Button variant="outline">Cancel</Button>
            <Button variant="subtle">Subtle</Button>
            <Button variant="ghost">Ghost</Button>
            <Button variant="link">Link</Button>
            <Button> <Mail class="w-4 h-auto mr-2 min-w-4" /> Login with Email</Button>

            <Button variant="icon"><Plus class="w-4 h-auto min-w-4" /></Button>
            <Button variant="iconCircle"><Plus class="w-4 h-auto min-w-4" /></Button>
            <Button variant="loading"
              ><Loader2 class="w-4 h-auto mr-2 min-w-4 animate-spin" />Loading</Button
            >
          </div>
        </div>

        <!-- Inputs -->

        <div class="bg-white rounded-md w-fit">
          <h1 class="p-4 text-xl font-semibold">Inputs</h1>
          <hr />
          <div class="flex flex-col items-start p-4 space-y-2 buttons">
            <Input variant="active" />
            <Input variant="disabled" />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import Button from "./components/Button.vue";
import Input from "./components/Input.vue";
import { Mail, Plus, Loader2 } from "lucide-vue-next";
</script>
