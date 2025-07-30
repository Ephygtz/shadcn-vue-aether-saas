<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: "End-to-End",
    title: "Holistic & End-to-End",
    description:
      "From initial concept and frontend design to robust backend development and AI-driven automation — we build the complete, integrated digital picture.",
    image: "roboto.png",
  },
  {
    badgeTitle: "Versatile",
    title: "Sector Versatility",
    description:
      "We deliver tailor-fit solutions across private, B2B, B2C, and government sectors, understanding the unique nuances of each domain.",
    image: "runner.png",
  },
  {
    badgeTitle: "Innovate",
    title: "Future-Proof Technology",
    description:
      "We leverage cutting-edge AI, robust cloud infrastructure, and zero-trust security to ensure your solutions are resilient and ready for tomorrow.",
    image: "pacheco.png",
  },
  {
    badgeTitle: "Collaborate",
    title: "Accelerated Impact",
    description:
      "Our agile development cycles and deep strategic alignment ensure rapid deployment of solutions that deliver immediate, measurable business value.",
    image: "gamestation.png",
  },
  {
    badgeTitle: "Global",
    title: "Global Standards",
    description:
      "We adhere to international best practices in software development and digital innovation. Our solutions are built to scale, ensuring your business can grow without limits.",
    image: "roboto.png",
  },
  {
    badgeTitle: "Partnership",
    title: "Dedicated Partnership",
    description:
      "We integrate as an extension of your team, ensuring open communication, transparent processes, and long-term success.",
    image: "runner.png",
  },
];
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        The Aether Sync Advantage
      </h2>

      <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
        We are more than a vendor; we are your strategic partner in growth. 
        Our unique approach ensures your digital transformation is not just successful, but sustainable and scalable.
      </h3>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="(
          { badgeTitle, title, description, image }, index
        ) in HowItWorksList"
        :key="title"
        :class="[
          'flex mb-8 items-center',
          { ' flex-row-reverse': index % 2 !== 0 },
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge>{{ badgeTitle }}</Badge>
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>

        <img
          :src="image"
          :alt="`Image describing ${title} `"
          className="w-[150px]  md:w-[250px] lg:w-[300px] mx-auto -scale-x-100 "
        />
        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>
  </section>
</template>
