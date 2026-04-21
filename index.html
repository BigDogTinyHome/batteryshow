import React, { useMemo, useState } from "react";

type Stop = {
  booth: string;
  company: string;
  priority: "Highest" | "High" | "Medium" | "Optional";
  companySummary: string;
  whatTheyDo: string;
  fit: string;
  whyInteresting: string;
  ask: string;
  notes: string[];
};

const STOPS: Stop[] = [
  {
    booth: "2123",
    company: "IMECAR",
    priority: "Highest",
    companySummary:
      "Full-stack electrification company spanning battery systems, power electronics, charging systems, embedded software, and broader vehicle and platform engineering.",
    whatTheyDo:
      "Full-stack electrification company working across battery systems, power electronics, charging systems, embedded software, and vehicle and platform engineering.",
    fit: "Best direct fit for chargebyte; electrification platform with charging relevance and fresh U.S. expansion.",
    whyInteresting:
      "Good target to understand whether they buy, build, or partner on charging communication, especially as they scale in the U.S. and potentially need modular controller solutions.",
    ask: "Do you currently build or source your EV charging controller and communication stack? How are you handling ISO 15118, Plug & Charge, OCPP 2.0.1, and future V2G?",
    notes: ["Strong partner target", "Controller-stack discussion", "Anchor meeting"],
  },
  {
    booth: "2035",
    company: "Solara Power",
    priority: "High",
    companySummary:
      "Provider of AC and DC EV charging solutions along with adjacent power electronics, storage, and supporting energy infrastructure offerings.",
    whatTheyDo:
      "Provides AC and DC EV chargers together with power electronics, energy storage, and related energy infrastructure solutions.",
    fit: "Explicit AC/DC EV charger company; strong EVSE conversation target.",
    whyInteresting:
      "One of the clearest EVSE manufacturer-type conversations on the floor, with a likely need for charging communication, controller integration, and future Plug & Charge roadmap support.",
    ask: "Are you building your own charge controller and comms stack, or sourcing it? What is your Plug & Charge and DC roadmap?",
    notes: ["Local NC company", "Best EVSE fit", "Ask about deployments"],
  },
  {
    booth: "1911",
    company: "AMPHERR AG",
    priority: "High",
    companySummary:
      "Battery-system and electrification specialist focused on commercial vehicle and industrial mobility use cases.",
    whatTheyDo:
      "Develops battery systems and electrification solutions focused on commercial vehicles and industrial mobility applications.",
    fit: "Commercial vehicle battery supplier; useful for vehicle-side charging intros and OEM context.",
    whyInteresting:
      "Relevant for vehicle-side charging communication discussions and potential introductions into commercial vehicle OEM or special-vehicle programs.",
    ask: "Which vehicle programs are driving your charging roadmap, and do you already have a preferred EVCC / charge communication architecture?",
    notes: ["Vehicle-side angle", "Commercial vehicle relevance", "Possible OEM intro"],
  },
  {
    booth: "1829",
    company: "Intertek",
    priority: "High",
    companySummary:
      "Global provider of testing, inspection, certification, and compliance services for EV, EVSE, battery, and electrical product programs.",
    whatTheyDo:
      "Global testing, inspection, certification, and compliance provider supporting EV, EVSE, battery, and electrical product programs.",
    fit: "Testing and certification leverage; useful for interoperability and certification intelligence.",
    whyInteresting:
      "Helpful for understanding certification bottlenecks, interoperability pain points, and how chargebyte can position itself as a lower-risk technology choice for OEMs and charger makers.",
    ask: "Where are EVSE and EV customers struggling most right now: interoperability, certification timing, cybersecurity, or standards implementation?",
    notes: ["Ecosystem leverage", "Market intelligence", "Future proof points"],
  },
  {
    booth: "1924",
    company: "Duke Energy",
    priority: "High",
    companySummary:
      "Major Southeastern utility active in EV programs, charging infrastructure initiatives, and grid-connected deployment planning.",
    whatTheyDo:
      "Major utility active in EV programs, charging infrastructure initiatives, and regional grid-facing deployment planning in the Southeast.",
    fit: "Regional ecosystem and utility perspective; useful for deployment expectations in the Southeast.",
    whyInteresting:
      "Strong ecosystem stop for understanding what utilities, fleets, and regional deployments increasingly expect from charging vendors and infrastructure partners.",
    ask: "What capabilities are utilities and fleet customers increasingly expecting from charging hardware vendors in the Southeast?",
    notes: ["Strong ecosystem contact", "Potential intros", "Regional market insight"],
  },
  {
    booth: "1735",
    company: "Anything EV",
    priority: "Medium",
    companySummary:
      "EV charging installer and services provider with hands-on visibility into deployment requirements, brand selection, and field issues.",
    whatTheyDo:
      "Offers EV charger installation, charging services, and deployment support, with practical visibility into customer requirements and field issues.",
    fit: "Installer and charging services view; useful for field intelligence on charger brands and pain points.",
    whyInteresting:
      "Less likely to be a direct controller buyer, but useful for channel intelligence on which charger brands are winning and where interoperability problems show up in real deployments.",
    ask: "Which charger brands are customers asking for most, and where do you see the biggest interoperability pain points?",
    notes: ["Channel insight", "Less direct buyer", "Good warm-up stop"],
  },
  {
    booth: "2111",
    company: "Hongfa America",
    priority: "Medium",
    companySummary:
      "Supplier of relays, contactors, and switching components used across EV charging, power electronics, and high-voltage systems.",
    whatTheyDo:
      "Supplies relays, contactors, and switching components widely used in EV charging, power electronics, and high-voltage applications.",
    fit: "Component supplier with EV relevance; useful for design trend and BOM benchmarking conversations.",
    whyInteresting:
      "Useful for benchmarking hardware design trends, learning what charger makers are specifying now, and spotting possible partner or supply-chain angles.",
    ask: "What EV charging design trends are you seeing most often in relay and power-path architecture right now?",
    notes: ["Component intelligence", "Possible partner angle", "Short stop"],
  },
  {
    booth: "2918",
    company: "TQ Systems USA",
    priority: "Optional",
    companySummary:
      "Engineering and embedded systems company supporting OEM solutions, including charging-management and energy-related system integration.",
    whatTheyDo:
      "Engineering and embedded systems company with OEM solution capability, including charging-management and energy-related system integration work.",
    fit: "Charging-management and OEM solution adjacency; useful only if time remains.",
    whyInteresting:
      "Worth a stop if time opens up, especially to understand where customers want modular control layers versus integrated end-to-end solutions.",
    ask: "Who usually owns the control layer in your charging projects, and where do customers prefer modular vs. integrated solutions?",
    notes: ["Adjacency only", "If time opens up", "Late-day detour"],
  },
];

const ROUTE = ["1735", "1829", "1911", "1924", "2035", "2111", "2123", "2918"];

const TIMELINE = [
  { time: "9:30-11:30", plan: "Anything EV -> Intertek -> AMPHERR" },
  { time: "11:30-1:00", plan: "Duke Energy -> Solara Power" },
  { time: "1:30-3:00", plan: "Hongfa -> IMECAR" },
  { time: "3:00-4:00", plan: "Optional TQ / revisit best booth / fill gaps" },
  { time: "4:30-6:00", plan: "Reception: OEM + EVSE networking" },
];

const PRIORITY_STYLES: Record<Stop["priority"], { bg: string; fg: string; border: string; dot: string }> = {
  Highest: { bg: "#fee2e2", fg: "#991b1b", border: "#fecaca", dot: "#ef4444" },
  High: { bg: "#ffedd5", fg: "#9a3412", border: "#fdba74", dot: "#f97316" },
  Medium: { bg: "#dbeafe", fg: "#1d4ed8", border: "#93c5fd", dot: "#3b82f6" },
  Optional: { bg: "#e2e8f0", fg: "#334155", border: "#cbd5e1", dot: "#94a3b8" },
};

const STORAGE_KEY = "battery-show-guide-visited";

function loadVisited(): Record<string, boolean> {
  if (typeof window === "undefined") return {};
  try {
    const raw = window.localStorage.getItem(STORAGE_KEY);
    return raw ? (JSON.parse(raw) as Record<string, boolean>) : {};
  } catch {
    return {};
  }
}

export default function BatteryShowChargebytePWA() {
  const orderedStops = useMemo(
    () => ROUTE.map((booth) => STOPS.find((stop) => stop.booth === booth)).filter(Boolean) as Stop[],
    []
  );

  const [visited, setVisited] = useState<Record<string, boolean>>(() => loadVisited());

  const toggleVisited = (booth: string) => {
    setVisited((current) => {
      const next = { ...current, [booth]: !current[booth] };
      if (typeof window !== "undefined") {
        window.localStorage.setItem(STORAGE_KEY, JSON.stringify(next));
      }
      return next;
    });
  };

  const visitedCount = STOPS.filter((stop) => visited[stop.booth]).length;

  return (
    <div style={styles.page}>
      <style>{globalStyles}</style>
      <div style={styles.shell}>
        <header style={styles.headerWrap}>
          <div style={styles.headerCard}>
            <p style={styles.eyebrow}>Battery Show South</p>
            <h1 style={styles.title}>Battery Show Guide</h1>
            <p style={styles.subtitle}>
              Simple guide to navigate the show, track conversations, and cover all key booths efficiently.
            </p>

            <div style={styles.kpiGrid}>
              <div style={styles.kpiCard}>
                <div style={styles.kpiLabel}>Top target</div>
                <div style={styles.kpiValue}>IMECAR</div>
                <div style={styles.kpiMeta}>Booth 2123</div>
              </div>
              <div style={styles.kpiCard}>
                <div style={styles.kpiLabel}>Best EVSE fit</div>
                <div style={styles.kpiValue}>Solara Power</div>
                <div style={styles.kpiMeta}>Booth 2035</div>
              </div>
            </div>

            <div style={styles.progressRow}>
              <div style={styles.progressLabel}>Visited</div>
              <div style={styles.progressValue}>{visitedCount} / {STOPS.length}</div>
            </div>
            <div style={styles.progressTrack}>
              <div style={{ ...styles.progressFill, width: `${(visitedCount / STOPS.length) * 100}%` }} />
            </div>
          </div>
        </header>

        <section style={styles.sectionCard}>
          <div style={styles.sectionHeader}>
            <h2 style={styles.sectionTitle}>Walking route</h2>
            <span style={styles.routeBadge}>Fast sweep</span>
          </div>
          <div style={styles.stackSmall}>
            {orderedStops.map((stop, i) => {
              const p = PRIORITY_STYLES[stop.priority];
              return (
                <label key={stop.booth} style={styles.routeRow}>
                  <div style={styles.routeIndex}>{i + 1}</div>
                  <div style={styles.routeMain}>
                    <div style={styles.routeTitleRow}>
                      <span style={{ ...styles.priorityDot, background: p.dot }} />
                      <span style={styles.routeCompany}>{stop.company}</span>
                    </div>
                    <div style={styles.routeMeta}>Booth {stop.booth}</div>
                  </div>
                  <span style={{ ...styles.priorityBadge, background: p.bg, color: p.fg, borderColor: p.border }}>
                    {stop.priority}
                  </span>
                  <input
                    type="checkbox"
                    checked={Boolean(visited[stop.booth])}
                    onChange={() => toggleVisited(stop.booth)}
                    aria-label={`Visited ${stop.company}`}
                    style={styles.checkbox}
                  />
                </label>
              );
            })}
          </div>
        </section>

        <section style={styles.sectionCard}>
          <h2 style={styles.sectionTitle}>Day plan</h2>
          <div style={styles.stackSmall}>
            {TIMELINE.map((slot) => (
              <div key={slot.time} style={styles.timelineCard}>
                <div style={styles.timelineTime}>{slot.time}</div>
                <div style={styles.timelinePlan}>{slot.plan}</div>
              </div>
            ))}
          </div>
        </section>

        <section>
          <div style={styles.sectionTopRow}>
            <h2 style={styles.sectionTitle}>Booth cards</h2>
            <div style={styles.sectionMeta}>Swipe-friendly stack</div>
          </div>

          <div style={styles.stackLarge}>
            {STOPS.map((stop) => {
              const p = PRIORITY_STYLES[stop.priority];
              return (
                <article key={stop.booth} style={styles.boothCard}>
                  <div style={styles.boothHeader}>
                    <div style={{ minWidth: 0 }}>
                      <div style={styles.boothLabel}>Booth {stop.booth}</div>
                      <h3 style={styles.boothCompany}>{stop.company}</h3>
                    </div>
                    <div style={styles.boothActions}>
                      <span style={{ ...styles.priorityBadge, background: p.bg, color: p.fg, borderColor: p.border }}>
                        {stop.priority}
                      </span>
                      <input
                        type="checkbox"
                        checked={Boolean(visited[stop.booth])}
                        onChange={() => toggleVisited(stop.booth)}
                        aria-label={`Visited ${stop.company}`}
                        style={styles.checkbox}
                      />
                    </div>
                  </div>

                  <div style={styles.stackSmall}>
                    <div style={styles.infoCard}>
                      <div style={styles.infoLabel}>What they do</div>
                      <p style={styles.infoText}>{stop.whatTheyDo}</p>
                    </div>

                    <div style={styles.infoCard}>
                      <div style={styles.infoLabel}>Why it matters</div>
                      <p style={styles.infoText}>{stop.whyInteresting}</p>
                    </div>

                    <details style={styles.infoCard}>
                      <summary style={styles.summaryLabel}>Company summary</summary>
                      <p style={{ ...styles.infoText, marginTop: 10 }}>{stop.companySummary}</p>
                    </details>

                    <div style={styles.infoCard}>
                      <div style={styles.infoLabel}>Quick fit</div>
                      <p style={styles.infoText}>{stop.fit}</p>
                    </div>

                    <div style={styles.infoCard}>
                      <div style={styles.infoLabel}>Opening question</div>
                      <p style={styles.askText}>“{stop.ask}”</p>
                    </div>
                  </div>

                  <div style={styles.tagWrap}>
                    {stop.notes.map((note) => (
                      <span key={note} style={styles.tag}>
                        {note}
                      </span>
                    ))}
                  </div>
                </article>
              );
            })}
          </div>
        </section>
      </div>
    </div>
  );
}

const globalStyles = `
  * { box-sizing: border-box; }
  html, body, #root { margin: 0; min-height: 100%; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    background: #f8fafc;
    color: #0f172a;
  }
  summary::-webkit-details-marker { display: none; }
`;

const styles: Record<string, React.CSSProperties> = {
  page: {
    minHeight: "100vh",
    background: "#f8fafc",
    color: "#0f172a",
  },
  shell: {
    maxWidth: 420,
    margin: "0 auto",
    padding: "12px 12px 112px",
  },
  headerWrap: {
    position: "sticky",
    top: 0,
    zIndex: 10,
    marginBottom: 12,
    paddingBottom: 12,
    background: "rgba(248,250,252,0.95)",
    backdropFilter: "blur(10px)",
  },
  headerCard: {
    background: "#ffffff",
    borderRadius: 24,
    padding: 16,
    border: "1px solid #e2e8f0",
    boxShadow: "0 3px 12px rgba(15, 23, 42, 0.06)",
  },
  eyebrow: {
    margin: 0,
    fontSize: 11,
    fontWeight: 700,
    letterSpacing: "0.18em",
    textTransform: "uppercase",
    color: "#64748b",
  },
  title: {
    margin: "6px 0 0",
    fontSize: 30,
    lineHeight: 1.05,
    fontWeight: 800,
  },
  subtitle: {
    margin: "10px 0 0",
    fontSize: 14,
    lineHeight: 1.5,
    color: "#475569",
  },
  kpiGrid: {
    display: "grid",
    gridTemplateColumns: "1fr 1fr",
    gap: 8,
    marginTop: 16,
  },
  kpiCard: {
    background: "#f1f5f9",
    borderRadius: 16,
    padding: 12,
  },
  kpiLabel: {
    fontSize: 11,
    textTransform: "uppercase",
    letterSpacing: "0.04em",
    color: "#64748b",
  },
  kpiValue: {
    marginTop: 4,
    fontSize: 14,
    fontWeight: 700,
  },
  kpiMeta: {
    fontSize: 12,
    color: "#64748b",
  },
  progressRow: {
    display: "flex",
    justifyContent: "space-between",
    alignItems: "center",
    marginTop: 14,
    marginBottom: 6,
  },
  progressLabel: {
    fontSize: 12,
    fontWeight: 600,
    color: "#475569",
  },
  progressValue: {
    fontSize: 12,
    fontWeight: 700,
    color: "#0f172a",
  },
  progressTrack: {
    height: 8,
    width: "100%",
    borderRadius: 999,
    background: "#e2e8f0",
    overflow: "hidden",
  },
  progressFill: {
    height: "100%",
    borderRadius: 999,
    background: "#0f172a",
  },
  sectionCard: {
    background: "#ffffff",
    borderRadius: 24,
    padding: 16,
    border: "1px solid #e2e8f0",
    boxShadow: "0 3px 12px rgba(15, 23, 42, 0.06)",
    marginBottom: 16,
  },
  sectionHeader: {
    display: "flex",
    alignItems: "center",
    justifyContent: "space-between",
    gap: 8,
  },
  sectionTitle: {
    margin: 0,
    fontSize: 20,
    fontWeight: 700,
  },
  routeBadge: {
    fontSize: 11,
    fontWeight: 600,
    color: "#475569",
    background: "#f1f5f9",
    borderRadius: 999,
    padding: "6px 10px",
  },
  stackSmall: {
    display: "flex",
    flexDirection: "column",
    gap: 10,
    marginTop: 12,
  },
  stackLarge: {
    display: "flex",
    flexDirection: "column",
    gap: 14,
  },
  routeRow: {
    display: "flex",
    alignItems: "center",
    gap: 10,
    border: "1px solid #e2e8f0",
    borderRadius: 18,
    padding: 12,
    background: "#ffffff",
  },
  routeIndex: {
    width: 32,
    height: 32,
    flexShrink: 0,
    borderRadius: 999,
    background: "#0f172a",
    color: "#ffffff",
    display: "flex",
    alignItems: "center",
    justifyContent: "center",
    fontSize: 12,
    fontWeight: 700,
  },
  routeMain: {
    minWidth: 0,
    flex: 1,
  },
  routeTitleRow: {
    display: "flex",
    alignItems: "center",
    gap: 8,
  },
  priorityDot: {
    width: 10,
    height: 10,
    borderRadius: 999,
    flexShrink: 0,
  },
  routeCompany: {
    fontSize: 14,
    fontWeight: 700,
    whiteSpace: "nowrap",
    overflow: "hidden",
    textOverflow: "ellipsis",
  },
  routeMeta: {
    marginTop: 2,
    fontSize: 12,
    color: "#64748b",
  },
  priorityBadge: {
    borderWidth: 1,
    borderStyle: "solid",
    borderRadius: 999,
    padding: "5px 9px",
    fontSize: 10,
    fontWeight: 700,
    whiteSpace: "nowrap",
  },
  checkbox: {
    width: 20,
    height: 20,
    flexShrink: 0,
    accentColor: "#0f172a",
  },
  timelineCard: {
    background: "#f1f5f9",
    borderRadius: 16,
    padding: 12,
  },
  timelineTime: {
    fontSize: 14,
    fontWeight: 700,
  },
  timelinePlan: {
    marginTop: 4,
    fontSize: 14,
    lineHeight: 1.5,
    color: "#475569",
  },
  sectionTopRow: {
    display: "flex",
    alignItems: "center",
    justifyContent: "space-between",
    marginBottom: 12,
  },
  sectionMeta: {
    fontSize: 12,
    color: "#64748b",
  },
  boothCard: {
    background: "#ffffff",
    borderRadius: 28,
    padding: 16,
    border: "1px solid #e2e8f0",
    boxShadow: "0 3px 12px rgba(15, 23, 42, 0.06)",
  },
  boothHeader: {
    display: "flex",
    alignItems: "flex-start",
    justifyContent: "space-between",
    gap: 12,
  },
  boothLabel: {
    fontSize: 12,
    color: "#64748b",
  },
  boothCompany: {
    margin: "4px 0 0",
    fontSize: 24,
    lineHeight: 1.1,
    fontWeight: 800,
  },
  boothActions: {
    display: "flex",
    alignItems: "flex-start",
    gap: 8,
    flexShrink: 0,
  },
  infoCard: {
    background: "#f8fafc",
    border: "1px solid #e2e8f0",
    borderRadius: 16,
    padding: 12,
  },
  infoLabel: {
    fontSize: 11,
    fontWeight: 700,
    textTransform: "uppercase",
    letterSpacing: "0.04em",
    color: "#64748b",
  },
  summaryLabel: {
    cursor: "pointer",
    listStyle: "none",
    fontSize: 11,
    fontWeight: 700,
    textTransform: "uppercase",
    letterSpacing: "0.04em",
    color: "#64748b",
  },
  infoText: {
    margin: "8px 0 0",
    fontSize: 14,
    lineHeight: 1.5,
    color: "#334155",
  },
  askText: {
    margin: "8px 0 0",
    fontSize: 14,
    lineHeight: 1.5,
    fontWeight: 600,
    color: "#0f172a",
  },
  tagWrap: {
    display: "flex",
    flexWrap: "wrap",
    gap: 8,
    marginTop: 14,
  },
  tag: {
    background: "#f1f5f9",
    borderRadius: 999,
    padding: "6px 10px",
    fontSize: 11,
    color: "#475569",
  },
};
