<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Full-Stack Web & Platform Development",
    description:
      "We craft bespoke, high-performance web applications and enterprise-grade digital platforms from concept to deployment. Our expertise spans stunning user interfaces and robust, scalable backend infrastructures, serving as the cornerstone of your digital presence. Includes: Custom websites, secure admin portals, powerful APIs, mobile-responsive applications, and cloud-native solutions.",
  },
  {
    icon: "badgeCheck",
    title: "B2B Software Solutions & Business Process Automation",
    description:
      "We empower businesses with intelligent, secure, and collaborative software tools designed to streamline workflows, optimize operational efficiency, and enhance inter-business ecosystems. Our solutions reduce manual effort and improve data flow. Includes: Custom CRM systems, secure supplier portals, intelligent inventory management, and comprehensive business process automation (BPA).",
  },
  {
    icon: "goal",
    title: "B2C Customer Experience & Engagement Platforms",
    description:
      "We design and develop highly intuitive, engaging platforms that bring businesses closer to their end-users. Our focus is on creating exceptional digital customer experiences, from seamless transactions to personalized interactions. Includes: Advanced e-commerce storefronts, secure online booking systems, dynamic subscription services, and vibrant digital communities.",
  },
  {
    icon: "pictureInPicture",
    title: "Public Sector & Government Digital Transformation",
    description:
      "Aether Sync is a trusted partner in e-governance. We develop secure, transparent, and user-centric digital platforms for government agencies to improve public service delivery, enhance data management, and foster greater citizen engagement. Includes: E-governance systems, secure digital registries, online licensing portals, and citizen service delivery platforms.",
  },
  {
    icon: "mousePointerClick",
    title: "AI Agent Integration & Intelligent Automation",
    description:
      "Step into the future with AI-powered business solutions. We specialize in integrating intelligent AI agents directly into your existing digital infrastructure to achieve cognitive automation and unlock unprecedented operational scale. Includes: Custom AI chatbots, predictive analytics dashboards, intelligent automation triggers, and machine learning integration.",
  },
  {
    icon: "newspaper",
    title: "B2B Automation",
    description:
      "B2B Solutions & Automation: We streamline inter-business workflows, from supplier portals to logistics, creating a seamless and efficient B2B ecosystem. Use Cases: Logistics firms, professional service providers, manufacturing companies, supply chain optimization.",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Features
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Our Core Solutions & Expertise
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      We provide end-to-end solutions to build your complete, integrated digital picture. 
      Explore our specialized capabilities designed for sector-specific challenges and opportunities.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
