<template>
  <div class="min-h-screen bg-background flex items-center justify-center p-4">
    <Card class="w-full max-w-md">
      <CardHeader>
        <CardTitle>Super Form (shadcn-vue)</CardTitle>
      </CardHeader>
      <CardContent>
        <form @submit.prevent="handleSubmit" class="space-y-6">
          <!-- Text Input -->
          <div class="space-y-2">
            <Label for="name">Name</Label>
            <Input
              id="name"
              placeholder="Enter your name"
              v-model="formData.name"
            />
          </div>

          <!-- Textarea -->
          <div class="space-y-2">
            <Label for="description">Description</Label>
            <Textarea
              id="description"
              placeholder="..."
              v-model="formData.description"
            />
          </div>

          <!-- Select -->
          <div class="space-y-2">
            <Label for="category">Category</Label>
            <Select v-model="formData.category">
              <SelectTrigger id="category">
                <SelectValue
                  :placeholder="
                    formData.category === 'none' ? 'Select a category' : ''
                  "
                />
              </SelectTrigger>
              <SelectContent>
                <SelectItem value="none">Select a category</SelectItem>
                <SelectItem value="technology">Technology</SelectItem>
                <SelectItem value="science">Science</SelectItem>
                <SelectItem value="art">Art</SelectItem>
              </SelectContent>
            </Select>
          </div>

          <!-- Range -->
          <div class="space-y-2">
            <Label for="rating">Rating: {{ formData.rating }}</Label>
            <Slider
              id="rating"
              v-model="formData.rating"
              :min="0"
              :max="10"
              :step="1"
              class="w-full"
            />
          </div>

          <!-- Radio Buttons -->
          <div class="space-y-2">
            <Label>Radio Button</Label>
            <RadioGroup v-model="formData.contactMethod">
              <div class="flex items-center space-x-2">
                <RadioGroupItem id="contact-email" value="email" />
                <Label for="contact-email">Select 1</Label>
              </div>
              <div class="flex items-center space-x-2">
                <RadioGroupItem id="contact-phone" value="phone" />
                <Label for="contact-phone">Select 2</Label>
              </div>
            </RadioGroup>
          </div>

          <!-- Checkbox -->
          <div class="flex items-center space-x-2">
            <Checkbox id="subscribe" v-model="formData.subscribe" />
            <Label for="subscribe">Subscribe</Label>
          </div>

          <!-- Submit Button -->
          <Button type="submit" class="w-full">Submit</Button>
        </form>
      </CardContent>
    </Card>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Card, CardHeader, CardTitle, CardContent } from "@/components/ui/card";
import { Label } from "@/components/ui/label";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import {
  Select,
  SelectTrigger,
  SelectValue,
  SelectContent,
  SelectItem,
} from "@/components/ui/select";
import { Slider } from "@/components/ui/slider";
import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group";
import { Checkbox } from "@/components/ui/checkbox";
import { Button } from "@/components/ui/button";

const formData = ref({
  name: "",
  description: "",
  category: "none",
  rating: [5],
  contactMethod: "",
  subscribe: false,
});

const handleSubmit = () => {
  console.log("Form submitted:", formData.value);
};
</script>
