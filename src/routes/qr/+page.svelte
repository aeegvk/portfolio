<svelte:head>
    <title>QR Code Generator</title>
    <meta name="description" content="Generate QR codes easily" />
</svelte:head>

<section>
    <h3>Enter a link to generate a QR Code</h3>
    <input type="text" placeholder="Enter a link" bind:value={link} />
    <button on:click={generateQrCode}>Generate QR Code</button>
    {#if $qrCodeData}
        <img src="{$qrCodeData}" alt="QR Code" />
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

    img {
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

<script>
    import { writable } from 'svelte/store';
    import QRCode from 'qrcode';

    let link = '';
    let qrCodeData = writable('');

    const generateQrCode = async () => {
        try {
            const options = {
                errorCorrectionLevel: 'H',
                width: 1024,
                margin: 2
            };
            const qrCode = await QRCode.toDataURL(link, options);
            qrCodeData.set(qrCode);
        } catch (error) {
            console.error('Error generating QR code', error);
        }
    };
</script>