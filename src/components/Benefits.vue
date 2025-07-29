<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "blocks",
    title: "Platform Dev",
    description:
      "Full-Stack Development: The cornerstone of your digital presence. We craft bespoke, high-performance web applications and enterprise-grade platforms..",
  },
  {
    icon: "lineChart",
    title: "B2C Engagement",
    description:
      "B2C Customer Platforms: We build engaging e-commerce, booking, and community platforms that connect you directly with your customers for exceptional experiences.",
  },
  {
    icon: "wallet",
    title: "E-Governance",
    description:
      "Public Sector Transformation: We develop secure, transparent e-governance systems that improve public service delivery and administrative efficiency.",
  },
  {
    icon: "sparkle",
    title: "AI Integration",
    description:
      "AI Agent Integration: We embed intelligent AI agents for cognitive automation, from advanced customer support chatbots to powerful data analytics assistants.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section
    id="benefits"
    class="container py-24 sm:py-32"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider">Benefits</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          From Digital Disconnect to Intelligent Synchronization
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
         Individual tools are not enough. True digital success is achieved when every component of your ecosystem—
         from customer touchpoints to backend logic—operates in perfect harmony. 
         We eliminate digital silos and automate complexity to create a single, intelligent, and optimized enterprise.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                class="size-8 mb-6 text-primary"
                :is="iconMap[icon]"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
