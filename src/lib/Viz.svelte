<script>
    import AudioMotionAnalyzer from 'audiomotion-analyzer';
    import {onMount} from "svelte";

    onMount(() =>  {
        // init audio motion analyzer
        const audioMotion = new AudioMotionAnalyzer(
            document.getElementById('canviz'),
            {
                source: document.getElementById('audio'),
                mode: 2,
                barSpace: 4,
                mirror: 1,
                outlineBars: true,
                alphaBars: true,
                overlay: true,
                showScaleX: false,
                showScaleY: false,
                showPeaks: true,
                fillAlpha: 0.1,
                ledBars: true,
            }
        );

        // reg themed gradient
        audioMotion.registerGradient('cool', {
            bgColor: 'rgba(66,66,66, 0.0)', colorStops: [
                'hsl( 208, 0%, 100% )',
                'hsl( 208, 100%, 35% )'
            ]
        });

        // update gradient option to "cool"
        audioMotion.setOptions({gradient: "cool"});
    });
</script>
