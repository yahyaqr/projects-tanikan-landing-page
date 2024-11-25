<template>
    <svg xmlns="http://www.w3.org/2000/svg" :width="width" :height="height" viewBox="0 0 150 50"
        preserveAspectRatio="none">
        <!-- SVG Content -->
        <rect width="100%" height="100%" :fill="background" />
        <text x="50%" y="50%" :fill="textColor" font-family="Arial, sans-serif" font-size="14"
            dominant-baseline="middle" text-anchor="middle">
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
            default: "100%", // Default to full width
        },
        height: {
            type: [String, Number],
            default: "100%", // Default to full height
        },
        background: {
            type: String,
            default: "#ddd", // Default to transparent background
        },
        text: {
            type: String,
            default: "Placeholder", // Default placeholder text
        },
        textColor: {
            type: String,
            default: "#888", // Default text color
        },
    },
};
</script>

<style scoped>
/* Dynamic max dimensions for the parent size */
svg {
    display: block;
    /* Removes inline SVG gaps */
    max-width: 100%;
    /* Dynamically constrained by the parent's width */
    max-height: 100%;
    /* Dynamically constrained by the parent's height */
    width: 100%;
    /* Scales to the parent's width by default */
    height: auto;
    /* Maintains aspect ratio */
}
</style>
