<template>
    <svg xmlns="http://www.w3.org/2000/svg" :width="width" :height="height" viewBox="0 0 150 50"
        preserveAspectRatio="none">
        <!-- SVG Content -->
        <rect width="100%" height="100%" :fill="background" />
        <text x="50%" y="50%" fill="#888" font-family="Arial, sans-serif" font-size="14" dominant-baseline="middle"
            text-anchor="middle">
            {{ text }}
        </text>
    </svg>
</template>

<script>
export default {
    name: "Placeholder",
    props: {
        width: {
            type: [String, Number],
            default: 64, // Default width in pixels
        },
        height: {
            type: [String, Number],
            default: 64, // Default height in pixels
        },
        text: {
            type: String,
            default: "Placeholder", // Default placeholder text
        },
        background: {
            type: String,
            default: "#ddd", // Default background color
        },
    },
};
</script>

<style scoped>
/* SVG default styling */
svg {
    display: block;
    /* Removes inline SVG gaps */
}
</style>
