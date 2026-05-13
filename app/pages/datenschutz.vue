<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'Datenschutz – GO.WEST Communications GmbH',
  ogTitle: 'Datenschutz – GO.WEST Communications GmbH',
  description: 'Datenschutzerklärung und Informationen zur Datenverarbeitung – GO.WEST Communications GmbH, Salzburg.',
  ogDescription: 'Datenschutzerklärung und Informationen zur Datenverarbeitung – GO.WEST Communications GmbH, Salzburg.'
})

function enterMotion(delay: number = 0) {
  return {
    initial: { opacity: 0, y: 16 },
    animate: { opacity: 1, y: 0 },
    transition: { duration: 0.6, delay }
  }
}

function scrollMotion(delay: number = 0) {
  return {
    initial: { opacity: 0, y: 16 },
    whileInView: { opacity: 1, y: 0 },
    inViewOptions: { once: true, amount: 0.05 },
    transition: { duration: 0.6, delay }
  }
}
</script>

<template>
  <div class="relative">
    <!-- Background dot grid overlay -->
    <div
      class="pointer-events-none fixed inset-0 opacity-[0.03] z-0"
      style="background-image: radial-gradient(rgba(139, 92, 246, 0.8) 1px, transparent 1px); background-size: 32px 32px;"
    />

    <!-- Hero -->
    <UPageHero
      :ui="{
        container: 'relative z-10 lg:py-20',
        wrapper: 'flex flex-col items-center',
        title: 'sm:text-5xl lg:text-6xl tracking-tighter leading-[1.1]',
        description: 'mt-3 max-w-xl mx-auto text-base leading-relaxed text-dimmed'
      }"
    >
      <template #top>
        <GradientGlow class="top-0 w-2/3 h-1/2" />
        <div class="pointer-events-none absolute -top-20 -left-32 w-[400px] h-[400px] rounded-full blur-[100px] bg-violet-500/[0.07]" />
        <div class="pointer-events-none absolute -top-10 -right-40 w-[300px] h-[300px] rounded-full blur-[80px] bg-fuchsia-500/[0.06]" />
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="enterMotion(0.35)"
          class="inline-block"
        >
          Datenschutz
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          Informationen zur Datenverarbeitung und zum Schutz Ihrer Daten
        </Motion>
      </template>
    </UPageHero>

    <!-- Content -->
    <UPageSection
      :ui="{
        container: 'max-w-2xl'
      }"
    >
      <Motion v-bind="scrollMotion(0)">
        <div class="space-y-16 text-sm leading-relaxed text-dimmed">
          <!-- Intro -->
          <div class="space-y-2">
            <p>
              In dieser Datenschutzrichtlinie von GO.WEST („Richtlinie") wird beschrieben, wie die GO.WEST Communications GmbH, mit Sitz in Panzerhalle, Siezenheimer Straße 39B, 5020 Salzburg, Österreich, (im Folgenden auch „GO.WEST", „wir", „uns", „unser" genannt) Daten über Sie beim Besuch unserer Websites („Website") erhebt und verarbeitet. Sie erklären sich durch die fortgesetzte Verwendung dieser Website mit der Verarbeitung Ihrer Daten gemäß dieser Richtlinie einverstanden.
            </p>
          </div>

          <!-- Datenschutz -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Datenschutz
            </h2>
            <p>
              Wir nehmen den Schutz Ihrer personenbezogenen Daten sehr ernst. Wir verarbeiten Ihre personenbezogenen Daten entsprechend der gesetzlichen Datenschutzvorschriften sowie dieser Datenschutzerklärung.
            </p>
            <p>
              Die Nutzung unserer Webseite ist in der Regel ohne Angabe personenbezogener Daten möglich. Soweit auf unseren Seiten personenbezogene Daten (beispielsweise Name, Anschrift oder E-Mail-Adressen) erhoben werden, erfolgt dies, soweit möglich, stets auf freiwilliger Basis.
            </p>
          </div>

          <!-- Datenschutzkoordinator -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Datenschutzkoordinator
            </h2>
            <p>
              Unseren Datenschutzkoordinator erreichen Sie unter:
            </p>
            <p class="pl-4">
              GO.WEST Communications GmbH
              <br>z.H. Datenschutzkoordinator
              <br>Panzerhalle
              <br>Siezenheimerstraße 39B
              <br>5020 Salzburg
              <br>Tel.: <a
                href="tel:+43662880540"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >+43-662-880540</a>
              <br>E-Mail: <a
                href="mailto:office@go-west.at"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >office@go-west.at</a>
            </p>
          </div>

          <!-- Auftragsverarbeiter -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Auftragsverarbeiter, Empfänger
            </h2>
            <p>
              Wir verarbeiten Ihre personenbezogenen Daten mit der Unterstützung von Auftragsverarbeitern, welche uns bei der Bereitstellung der Dienste unterstützen (z.B. Webhoster, E-Mail-Newsletter-Versanddienst).
            </p>
            <ul class="list-disc list-inside space-y-1 pl-4">
              <li>Hetzner Online GmbH / xLab Software Engineering</li>
              <li>Cloudflare, Inc</li>
              <li>CleverReach</li>
              <li>Google</li>
              <li>Hotjar</li>
              <li>Adobe</li>
            </ul>
            <p>
              Diese Auftragsverarbeiter sind zum strengen Schutz Ihrer personenbezogenen Daten verpflichtet und dürfen Ihre personenbezogenen Daten zu keinem anderen Zweck als zur Bereitstellung unserer Dienste verarbeiten.
            </p>
            <p>
              Eine Weitergabe Ihrer personenbezogenen Daten erfolgt nur an wirtschaftstypische Dienstleister wie z.B. Banken (im Fall von Überweisungen an Sie), Steuerberater (falls Sie in unserer Buchhaltung vorkommen), Versanddienstleister (im Fall der Versendung an Sie), etc.
            </p>
          </div>

          <!-- Kontaktformular -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Kontaktformular
            </h2>
            <p>
              Nach Absenden des Kontaktformulars erfolgt eine Verarbeitung der von Ihnen eingegebenen personenbezogenen Daten durch den datenschutzrechtlich Verantwortlichen zum Zweck der Bearbeitung Ihrer Anfrage auf Grundlage Ihrer durch das Absenden des Formulars erteilten Einwilligung.
            </p>
            <p>
              Es besteht keine gesetzliche oder vertragliche Verpflichtung zur Bereitstellung der personenbezogenen Daten. Die Nichtbereitstellung hat lediglich zur Folge, dass Sie Ihr Anliegen nicht übermitteln und wir dieses nicht bearbeiten können.
            </p>
            <p>
              Sie haben das Recht, Ihre Einwilligung jederzeit durch schriftliche Mitteilung zu widerrufen, ohne dass die Rechtmäßigkeit der aufgrund der Einwilligung bis zum Widerruf erfolgten Verarbeitung berührt wird.
            </p>
            <p>
              Es erfolgt eine Weiterverarbeitung der Daten, welche mit dem ursprünglichen Verarbeitungszweck vereinbar ist, auf derselben Rechtsgrundlage, bis auf Widerspruch. In diesem Fall erfolgt eine Weitergabe der Daten an den Versanddienstleister.
            </p>
            <p>
              Sie haben das Recht, der Verwendung Ihrer personenbezogenen Daten zum Zweck der Direktwerbung jederzeit durch schriftliche Mitteilung zu widersprechen. Im Fall des Widerspruchs werden Ihre personenbezogenen Daten nicht mehr zum Zweck der Direktwerbung verarbeitet.
            </p>
          </div>

          <!-- E-Mail-Newsletter -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              E-Mail-Newsletter
            </h2>
            <p>
              Durch Ankreuzen der Checkbox willigen Sie in die Verarbeitung der von Ihnen eingegebenen personenbezogenen Daten zum Zweck der Information über Angebote, Neuigkeiten und Trends mittels eines E-Mail-Newsletters durch den datenschutzrechtlich Verantwortlichen bis auf Widerruf bzw. Widerspruch ein.
            </p>
            <p>
              Es besteht keine gesetzliche oder vertragliche Verpflichtung zur Bereitstellung der personenbezogenen Daten. Die Nichteinwilligung hat lediglich zur Folge, dass Sie keinen E-Mail-Newsletter erhalten.
            </p>
            <p>
              Sie haben das Recht, Ihre Einwilligung jederzeit durch schriftliche Mitteilung oder durch Klick auf den Abmeldelink im E-Mail-Newsletter zu widerrufen, ohne dass die Rechtmäßigkeit der aufgrund der Einwilligung bis zum Widerruf erfolgten Verarbeitung berührt wird.
            </p>
            <p>
              Ebenso können Sie der Verwendung Ihrer personenbezogenen Daten zum Zweck der Direktwerbung auf selbe Weise widersprechen. Im Fall des Widerspruchs werden Ihre personenbezogenen Daten nicht mehr zum Zweck der Direktwerbung in Form eines E-Mail-Newsletters verarbeitet.
            </p>
          </div>

          <!-- Server Logfile -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Server Logfile
            </h2>
            <p>
              Diese Website verarbeitet zum Zweck der Überwachung der technischen Funktion und zur Erhöhung der Betriebssicherheit des Webservers auf Grundlage des überwiegenden berechtigten Interesses des Verantwortlichen (technische Sicherheitsmaßnahmen) folgende personenbezogene Daten in einer Protokolldatei am Server:
            </p>
            <ul class="list-disc list-inside space-y-1 pl-4">
              <li>aufgerufener Inhalt</li>
              <li>Uhrzeit der Serveranfrage</li>
              <li>Browsertyp / Browserversion</li>
              <li>verwendetes Betriebssystem</li>
              <li>HTTP Referrer</li>
              <li>IP-Adresse oder Hostname</li>
            </ul>
            <p>
              Diese Daten werden nur temporär für die Dauer von 10 Tagen gespeichert. Danach werden die Daten automatisiert gelöscht.
            </p>
          </div>

          <!-- Google Analytics -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Google Analytics
            </h2>
            <p>
              Diese Website verwendet Google Analytics, einen Webanalysedienst der Google LCC („Google") auf der Rechtsgrundlage des überwiegenden berechtigten Interesses (Analyse der Websitenutzung). Wir haben dazu mit Google einen Vertrag zur Auftragsdatenverarbeitung abgeschlossen.
            </p>
            <p>
              Beim Aufruf unserer Webseite wird über eine Software eine Verbindung zu den Servern von Google hergestellt und Daten an teils in den USA befindliche Server von Google übermittelt. Google Analytics verwendet zudem Cookies zur Speicherung von Informationen über den Website-Benutzer und zur Analyse der Benutzung der Website durch die Website-Benutzer.
            </p>
            <p>
              Diese Website nutzt die Funktion "IP-Anonymisierung". Dadurch wird Ihre IP-Adresse von Google innerhalb von Mitgliedstaaten der Europäischen Union oder in anderen Vertragsstaaten des Abkommens über den Europäischen Wirtschaftsraum zuvor gekürzt und damit anonymisiert. Nur in Ausnahmefällen wird die volle IP-Adresse an einen Server von Google in den USA übertragen und dort gekürzt.
            </p>
            <p>
              Laut Angaben von Google wird Google die erhobenen Daten benutzen, um die Nutzung der Website auszuwerten, um Reports über die Websiteaktivitäten zusammenzustellen und um weitere mit der Websitenutzung und der Internetnutzung verbundene Dienstleistungen zu erbringen.
            </p>
            <p>
              Auch wird Google diese Informationen gegebenenfalls an Dritte übertragen, sofern dies gesetzlich vorgeschrieben ist oder soweit Dritte diese Daten im Auftrag von Google verarbeiten.
            </p>
            <p>
              Detaillierte Informationen zum Umgang mit Nutzerdaten bei Google Analytics finden Sie in der Datenschutzerklärung von Google bzw. von Google Analytics.
            </p>
          </div>

          <!-- Facebook Pixel -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Facebook Pixel
            </h2>
            <p>
              Diese Website verwendet Facebook Pixel, einen Webanalysedienst der Facebook Ireland Limited („Facebook") auf der Rechtsgrundlage des überwiegenden berechtigten Interesses (Analyse der Websitenutzung).
            </p>
            <p>
              Die Daten werden teilweise in die USA übertragen. Die Übermittlung der Daten in die USA erfolgt auf Grundlage des Privacy Shields.
            </p>
            <p>
              Beim Aufruf unserer Webseite wird über eine Software eine Verbindung zu den Servern von Facebook hergestellt und Daten an teils in den USA befindlichen Server von Facebook übermittelt. Facebook Pixel verwendet zudem Cookies zur Speicherung von Informationen über den Website-Benutzer und zur Analyse der Benutzung der Website durch die Website-Benutzer.
            </p>
            <p>
              Laut Angaben von Facebook wird Facebook die erhobenen Daten benutzen, um die Nutzung der Website auszuwerten, um Reports über die Websiteaktivitäten zusammenzustellen und um weitere mit der Websitenutzung und der Internetnutzung verbundene Dienstleistungen zu erbringen.
            </p>
            <p>
              Auch wird Facebook diese Informationen gegebenenfalls an Dritte übertragen, sofern dies gesetzlich vorgeschrieben ist oder soweit Dritte diese Daten im Auftrag von Facebook verarbeiten.
            </p>
            <p>
              Detaillierte Informationen zum Umgang mit Nutzerdaten bei Facebook finden Sie in der Datenschutzerklärung von Facebook.
            </p>
          </div>

          <!-- Hotjar -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Hotjar
            </h2>
            <p>
              Diese Website verwendet Hotjar, einen Webanalysedienst der Hotjar Ltd. („Hotjar") auf der Rechtsgrundlage des überwiegenden berechtigten Interesses (Analyse der Websitenutzung). Wir haben dazu mit Hotjar einen Vertrag zur Auftragsdatenverarbeitung abgeschlossen.
            </p>
            <p>
              Beim Aufruf unserer Webseite wird über eine Software eine Verbindung zu den Servern von Hotjar hergestellt und Daten an in der EU befindliche Server von Hotjar übermittelt. Hotjar verwendet zudem Cookies zur Speicherung von Informationen über den Website-Benutzer und zur Analyse der Benutzung der Website durch die Website-Benutzer.
            </p>
            <p>
              Laut Angaben von Hotjar wird Hotjar die erhobenen Daten benutzen, um die Nutzung der Website auszuwerten, um Reports über die Websiteaktivitäten zusammenzustellen und um weitere mit der Websitenutzung und der Internetnutzung verbundene Dienstleistungen zu erbringen.
            </p>
            <p>
              Detaillierte Informationen zum Umgang mit Nutzerdaten bei Hotjar finden Sie in der Datenschutzerklärung von Hotjar.
            </p>
            <p>
              Sie können die Erfassung Ihrer Nutzerdaten generell verhindern, indem Sie in Ihrem Webbrowser „Do Not Track" einstellen. Hotjar berücksichtigt das „Do Not Track"-Signal, das Ihr Webbrowser dann an alle Websites sendet.
            </p>
            <p>
              Sie können die Erfassung Ihrer Nutzerdaten durch Hotjar generell auf allen Websites verhindern, indem Sie die Software direkt auf der Hotjar-Website deaktivieren: <a
                href="https://www.hotjar.com/legal/compliance/opt-out"
                target="_blank"
                rel="noopener noreferrer"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >https://www.hotjar.com/legal/compliance/opt-out</a>
            </p>
          </div>

          <!-- Teilen-Buttons -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Teilen-Buttons
            </h2>
            <p>
              Unsere Website verfügt auf manchen Seiten über Buttons zum Teilen der Seiteninhalte auf den Social Media-Plattformen Facebook, Google Plus, Instagram, Linkedin, Pinterest, Tumblr, Twitter, XING und Youtube.
            </p>
            <p>
              Die Buttons sind im Sinn des Schutzes der personenbezogenen Daten unserer Websitebesucher ideal ausgestaltet, da das hinter den Buttons liegende Skript (Computerprogramm) keine personenbezogenen Daten erfasst oder verarbeitet. Websitebesucher, die unsere Seite teilen wollen, werden bei Klick auf die Buttons direkt auf die „Teilen"-Seiten der jeweiligen Social Media-Plattformen geleitet. Erst dort werden die zum Teilen der Seiteninhalte notwendigen Skripte geladen. Dabei gelten dann die vom Websitebesucher mit den jeweiligen Social Media-Plattformen vereinbarten Geschäfts- und Datenschutzbedingungen. Genaue Informationen darüber bieten die jeweiligen Plattformen:
            </p>
            <ul class="list-disc list-inside space-y-1 pl-4">
              <li>Facebook</li>
              <li>Google Plus</li>
              <li>Instagram</li>
              <li>Linkedin</li>
              <li>Pinterest</li>
              <li>Twitter</li>
              <li>XING</li>
            </ul>
          </div>

          <!-- Ihre Rechte -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Ihre Rechte
            </h2>
            <p>
              Sie haben das Recht auf Auskunft, Berichtigung, Löschung und Einschränkung der Verarbeitung der personenbezogenen Daten.
            </p>
            <p>
              Soweit die Rechtsgrundlage der Verarbeitung Ihrer personenbezogenen Daten in Ihrer Einwilligung oder in einem mit Ihnen abgeschlossenen Vertrag besteht, haben Sie zudem das Recht auf Datenübertragbarkeit.
            </p>
            <p>
              Sie haben das Recht auf Widerruf einer eventuell erteilten Einwilligung zur Verarbeitung Ihrer personenbezogenen Daten. Die Rechtmäßigkeit der Verarbeitung der personenbezogenen Daten bis zum Widerruf wird durch den Widerruf nicht berührt.
            </p>
            <p>
              Sie haben das Recht auf Widerspruch gegen die Verarbeitung Ihrer personenbezogenen Daten zum Zweck der Direktwerbung. Im Fall des Widerspruchs werden Ihre personenbezogenen Daten nicht mehr zum Zwecke der Direktwerbung verarbeitet.
            </p>
            <p>
              Weiters haben Sie das Recht auf Beschwerde bei der Aufsichtsbehörde (Österreichische Datenschutzbehörde, Wickenburggasse 8, 1080 Wien, <a
                href="mailto:dsb@dsb.gv.at"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >dsb@dsb.gv.at</a>).
            </p>
          </div>
        </div>
      </Motion>
    </UPageSection>

    <!-- Ambient glow bottom -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-5%] w-[600px] h-[600px] rounded-full blur-[100px] bg-violet-500/[0.06]" />
      <div class="absolute -top-20 left-[-10%] w-[350px] h-[350px] rounded-full blur-[80px] bg-fuchsia-400/[0.04]" />
    </div>
  </div>
</template>
