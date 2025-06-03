<template>
    <BackgroundImage :disable="false" :blur="bluring" />
    <FullscreenSize class="container-app">
        <div class="main" :class="{ bluring }" @mouseover="bluring = true" @mouseleave="bluring = false">
            <AvatarImage /><br>
            <NameLabel>曾梓琳</NameLabel><br>
            <BlockLabel>重庆市</BlockLabel>
            <BlockLabel>南岸区</BlockLabel>
            <BlockLabel>中海学校</BlockLabel><br>
            <CatcherText>好看的皮囊千篇一律，有趣的灵魂万里挑一</CatcherText>
            <DescriptionParagraph title="关于我">
                你好！<br>
                我是<b>小松鼠蹦蹦</b>，来自中海学校的 <i>数学</i> 爱好者。<br>
                有梦想，但没学😭，无法实现。
            </DescriptionParagraph>
            <DescriptionParagraph title="技能">
                用 <b>114514秒</b> 推算出了二次函数第三问🤓。<br>
                目前能熟练使用的一些吊炸天的 <b>公式/定理</b>：<br>
                <BlockLabel>三角函数</BlockLabel>
                <BlockLabel>平方差/完全平方</BlockLabel>
                <BlockLabel>二次方程求根公式</BlockLabel>
                <VerticalLine />
                <BlockLabel>勾股定理💀</BlockLabel>
                <BlockLabel>韦达定理🍞</BlockLabel>
                <BlockLabel>弦切角定理✨</BlockLabel>
            </DescriptionParagraph>
            <DescriptionParagraph title="展望">
                熊出没激推！<br>
                <SearchE621 target="#">蹦蹦</SearchE621>
                <SearchE621 target="#">熊大</SearchE621>
                <SearchE621 target="#">熊二</SearchE621><br>
                <OutLink href="oc.jpg">
                    <template #prompt>
                        <img src="oc.jpg" class="oc-preview">
                    </template>
                    自设/OC：小松鼠蹦蹦
                </OutLink>
            </DescriptionParagraph>
            <DescriptionParagraph title="联系方式">
                邮箱：<OutLink>没有</OutLink><br>
                QQ：<OutLink>没有</OutLink><br>
                <OutLink>哔哩哔哩（没有）</OutLink>
                <OutLink>Github（没有）</OutLink>
            </DescriptionParagraph>
            <HorizontalLine />
            <BigTitle>development</BigTitle><br>
            <ProjectCard title="二次函数" tech-stack="顶点式" category="函数">
                设个解析式🤓☝️解方程组🤓☝️解关键点🤓☝️求新函数最值🤓☝️
            </ProjectCard>
            <ProjectCard title="几何大题" tech-stack="辅助线" category="几何">
                做辅助线🤓☝️画图🤓☝️求面积🤓☝️求周长🤓☝️求最值🤓☝️
            </ProjectCard>
            <ProjectCard title="垂径定理" tech-stack="圆切线" category="几何">
                画图🤓☝️求垂径🤓☝️求弦长🤓☝️求半径🤓☝️求最值🤓☝️
            </ProjectCard>
            <HorizontalLine />
            <BigTitle>友情链接</BigTitle><br>
            <OutLink href="https://fshrimp.fun">Templated from F-Shrimp</OutLink><br>
            <OutLink href="https://vuejs.org">Vue</OutLink>
            +
            <OutLink href="https://webpackjs.com">Webpack</OutLink>
        </div>
    </FullscreenSize>
</template>
<script setup lang="ts">
import { ref } from "vue";
import AvatarImage from "./AvatarImage.vue";
import BackgroundImage from "./BackgroundImage.vue";
import FullscreenSize from "./FullscreenSize.vue";
import NameLabel from "./NameLabel.vue";
import BlockLabel from "./BlockLabel.vue";
import CatcherText from "./CatcherText.vue";
import DescriptionParagraph from "./DescriptionParapragh.vue";
import VerticalLine from "./VerticalLine.vue";
import OutLink from "./OutLink.vue";
import HorizontalLine from "./HorizontalLine.vue";
import ProjectCard from "./ProjectCard.vue";
import BigTitle from "./BigTitle.vue";
import SearchE621 from "./SearchE621.vue";
const bluring = ref(false);
function copy(data: string) {
    try {
        window.navigator.clipboard.writeText(data);
    } catch {
        alert("复制失败。");
    }
};
window.mouse = ref([0, 0]);
window.addEventListener("mousemove", (e) => {
    window.mouse.value = [e.clientX, e.clientY];
});
</script>
<style scoped>
.container-app {
    text-align: center;
    width: 100%;
    height: auto;
    position: absolute;
}

.main.bluring {
    opacity: 1;
}

.main {
    padding: 50px 0;
    display: inline-block;
}

.link-2 {
    margin-left: 5px;
}

.oc-preview {
    width: 200px;
    display: block;
}

.text-left {
    text-align: left;
    width: fit-content;
    display: inline-block;
}
</style>