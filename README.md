Consent Manager Installation Instructions

1. Extract the contents of this zip file
2. Place the files in your website directory
3. Add the following code to your HTML page, inside the <head> tag:

<link rel="stylesheet" id="silktide-consent-manager-css" href="path-to-css/silktide-consent-manager.css">
<script src="path-to-js/silktide-consent-manager.js"></script>
<script>
silktideCookieBannerManager.updateCookieBannerConfig({
  background: {
    showBackground: true
  },
  cookieIcon: {
    position: "bottomLeft"
  },
  cookieTypes: [
    {
      id: "n_dv_ndiga",
      name: "Nödvändiga",
      description: "<p>Nödvändiga cookies låter dig använda webbplatsen genom att aktivera grundläggande funktioner, såsom sidnavigering och åtkomst till säkra områden på webbplatsen. Webbplatsen fungerar inte korrekt utan dessa cookies.</p>",
      required: true,
      onAccept: function() {
        console.log('Add logic for the required Nödvändiga here');
      }
    },
    {
      id: "inst_llningar",
      name: "Inställningar",
      description: "<p class=\"p1\" style=\"margin-bottom: 0px; font-variant-numeric: normal; font-variant-east-asian: normal; font-variant-alternates: normal; font-size-adjust: none; font-kerning: auto; font-optical-sizing: auto; font-feature-settings: normal; font-variation-settings: normal; font-variant-position: normal; font-variant-emoji: normal; font-stretch: normal; line-height: normal;\">Cookies för inställningar låter en webbplats komma ihåg information som ändrar hur webbplatsen fungerar eller visas. Detta kan t.ex. vara föredraget språk eller regionen du befinner dig i.</p>",
      required: false,
      onAccept: function() {
        gtag('consent', 'update', {
          functionality_storage: 'granted',
        });
        dataLayer.push({
          'event': 'consent_accepted_inst_llningar',
        });
      },
      onReject: function() {
        gtag('consent', 'update', {
          functionality_storage: 'denied',
        });
      }
    },
    {
      id: "marknadsf_ring",
      name: "Marknadsföring",
      description: "<p>\n\n\n\n\n\n\n\n</p><blockquote style=\"margin: 0px 0px 0px 15px; font-variant-numeric: normal; font-variant-east-asian: normal; font-variant-alternates: normal; font-size-adjust: none; font-kerning: auto; font-optical-sizing: auto; font-feature-settings: normal; font-variation-settings: normal; font-variant-position: normal; font-variant-emoji: normal; font-stretch: normal; line-height: normal;\">Vi använder cookies för statistik och för att kunna visa relevant innehåll och annonser längre fram.</blockquote>",
      required: false,
      onAccept: function() {
        gtag('consent', 'update', {
          ad_storage: 'granted',
          ad_user_data: 'granted',
          ad_personalization: 'granted',
        });
        dataLayer.push({
          'event': 'consent_accepted_marknadsf_ring',
        });
      },
      onReject: function() {
        gtag('consent', 'update', {
          ad_storage: 'denied',
          ad_user_data: 'denied',
          ad_personalization: 'denied',
        });
      }
    }
  ],
  text: {
    banner: {
      description: "<p class=\"p1\" style=\"margin-bottom: 0px; font-variant-numeric: normal; font-variant-east-asian: normal; font-variant-alternates: normal; font-size-adjust: none; font-kerning: auto; font-optical-sizing: auto; font-feature-settings: normal; font-variation-settings: normal; font-variant-position: normal; font-variant-emoji: normal; font-stretch: normal; line-height: normal;\">För att ge dig den bästa upplevelsen använder vi cookies som hjälper oss förbättra sidan och visa innehåll som är relevant för dig. Du kan alltid justera dina inställningar senare.</p>",
      acceptAllButtonText: "Acceptera alla",
      acceptAllButtonAccessibleLabel: "Accept all cookies",
      rejectNonEssentialButtonText: "Avvisa alla",
      rejectNonEssentialButtonAccessibleLabel: "Reject non-essential",
      preferencesButtonText: "Preferenser",
      preferencesButtonAccessibleLabel: "Toggle preferences"
    },
    preferences: {
      title: "Skräddarsy dina cookie preferenser",
      description: "<p class=\"p1\" style=\"margin-bottom: 0px; font-variant-numeric: normal; font-variant-east-asian: normal; font-variant-alternates: normal; font-size-adjust: none; font-kerning: auto; font-optical-sizing: auto; font-feature-settings: normal; font-variation-settings: normal; font-variant-position: normal; font-variant-emoji: normal; font-stretch: normal; line-height: normal;\">Vi värnar om din integritet. Du bestämmer själv vilka cookies du vill tillåta, och dina inställningar gäller på hela vår webbplats.</p>",
      creditLinkText: "Get this banner for free",
      creditLinkAccessibleLabel: "Get this banner for free"
    }
  }
});
</script>
