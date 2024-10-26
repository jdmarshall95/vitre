<template>
  <div class="max-w-screen overflow-x-hidden py-24 text-[#ffd68a]">
    <p class="text-[18vw] leading-none break-words break-all">
      Идет третий век Зеленой Эры. Имплант-коррекция «Открытого Мозга» превратила женщин в доминантный гендер, и в уголовной иерархии изменился баланс сил. На ее вершину поднялся фем-блатняк — безжалостные куры-заточницы. Противостоять им не может никто из биологических мужчин, но есть нюанс. Маркус Зоргенфрей — лучший баночный оперативник «TRANSHUMANISM INC.». Задания, которые поручает ему адмирал-епископ Ломас, настолько чувствительны, что после них ему стирают память. Он не стал бы вникать в арестантские разборки, если бы не страшная опасность, нависшая над планетой. Как связаны разрушенный Светом ад и Мезозой? Что такое магия высших духов? Почему древнее зло нашло себе новое воплощение в сибирской ветроколонии? При чем здесь могила Париса, демон Ахилла и в чем тайна зловещей Варвары Цугундер, которую куры-заточницы считают своим ментором уже сотни лет? Остросюжетный триллер-детектив «Круть» даст ответ на многие мучительные вопросы, которых никто еще не решался задать.
    </p>
  </div>
  <div class="fixed top-0 left-0 right-0 bottom-0 w-full h-svh flex justify-center items-center z-10">
    <div class="w-screen h-screen p-8 box-border max-w-full max-h-full">
      <FlutedGlass :type="glassType">
        <div class="flex items-center space-x-2">
          <Select v-model:model-value="glassType">
            <SelectTrigger>
              <SelectValue placeholder="Я зочу заказать питсу." />
            </SelectTrigger>
            <SelectContent>
              <SelectItem
                v-for="t in types"
                :key="t"
                :value="t">
                {{ translations[t] || t }}
              </SelectItem>
            </SelectContent>
          </Select>
        </div>
        <div >
          <Select >
            <SelectTrigger>
              <SelectValue placeholder="Соус будет к пицце?" />
            </SelectTrigger>
            <SelectContent>
              <SelectItem
                v-for="sauce in sauces"
                :key="sauce"
                :value="sauce">
                {{ sauce }}
              </SelectItem>
            </SelectContent>
          </Select>
        </div>
        <div class="py-16">
      <Switch
      v-model="enabled"
      :class="enabled ? 'bg-teal-900' : 'bg-teal-700'"
      class="relative inline-flex h-[38px] w-[74px] shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus-visible:ring-2 focus-visible:ring-white/75"
        >
          <span class="sr-only">Use setting</span>
        <span
        aria-hidden="true"
        :class="enabled ? 'translate-x-9' : 'translate-x-0'"
        class="pointer-events-none inline-block h-[34px] w-[34px] transform rounded-full bg-white shadow-lg ring-0 transition duration-200 ease-in-out"
        />
        </Switch>
      </div>

      </FlutedGlass>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, Ref } from 'vue'
import { Icon } from '@iconify/vue'
import { Button } from './components/ui/button'
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select'
import FlutedGlass, { FlutedGlassType } from './components/FlutedGlass.vue'

const types: FlutedGlassType[] = [
  'fluted',
  'cross',
  'romb',
  'circle',
]

const translations = {
  fluted: 'Дорблю',
  cross: 'Эмменталь',
  romb: 'Чеддер',
  circle: 'Моцарелочка',
};

const sauces = [
  'томатный',
  'муйянез',
]

const glassType: Ref<FlutedGlassType | undefined> = ref(undefined)

import { Switch } from '@headlessui/vue'

const enabled = ref(false)

import {
  Listbox,
  ListboxLabel,
  ListboxButton,
  ListboxOptions,
  ListboxOption,
} from '@headlessui/vue'

import { CheckIcon, ChevronUpDownIcon } from '@heroicons/vue/20/solid'

const people = [
  { name: 'Wade Cooper' },
  { name: 'Arlene Mccoy' },
  { name: 'Devon Webb' },
  { name: 'Tom Cook' },
  { name: 'Tanya Fox' },
  { name: 'Hellen Schmidt' },
]
const selectedPerson = ref(people[0])

</script>

