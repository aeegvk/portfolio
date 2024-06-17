<svelte:head>
    <title>QR Code Generator</title>
    <meta name="description" content="Generate QR codes easily" />
</svelte:head>

<section>
    <h3>Enter a link to generate a QR Code</h3>
    <input type="text" placeholder="Enter a link" bind:value={link} />
    <input type="text" placeholder="Enter custom text" bind:value={customText} />
    <button on:click={generateQrCode}>Generate QR Code</button>
    {#if link}
        <canvas bind:this={canvas}></canvas>
        <a href="#" bind:this={downloadLink}>Download QR Code</a>
    {/if}
</section>

<style>
    section {
        width: 17em;
        font-size: 2em;
        font-weight: 100;
        text-align: right;
        vertical-align: bottom;
        position: absolute;
        bottom: 2rem;
        right: 5rem;
    }

    input, button {
        font-size: 1em;
        margin: 1em;
    }

    canvas {
        margin-top: 1em;
        width: 10em;
    }

    /* On screens that are 600px or less, set the background color to olive */
    @media screen and (max-width: 600px) {
        section {
            bottom: 0em;
            right: 1em;
            width: 80%;
            font-size: 1em;
        }
    }
</style>

<script lang="ts">
    import { onMount } from 'svelte';
    import QRCode from 'qrcode';

    let link = '';
    let customText = '';
    let canvas;
    let downloadLink;

    const generateQrCode = async () => {
        try {
            const options = {
                errorCorrectionLevel: 'H',
                width: 512,
                margin: 2
            };
            await QRCode.toCanvas(canvas, link, options);
            const ctx = canvas.getContext('2d');
            if (ctx) {
                ctx.font = '27px Arial';
                const textWidth = ctx.measureText(customText).width;
                const posX = 7;
                const posY = canvas.height - 7;
                ctx.fillText(customText, posX, posY);
            }
            downloadLink.href = canvas.toDataURL();
            downloadLink.download = 'qrcode.png';
        } catch (error) {
            console.error('Error generating QR code', error);
        }
    };
</script>