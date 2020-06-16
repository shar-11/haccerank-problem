# haccerank-problem

	boolean debug = false;
	
	int mem_size = 20;
	double consid_rate = 0.95; 
	double adjust_rate = 0.7; 
	double range = 0.05;
	int max_iter = 0;
	int factor = 1;
	Random random;
	
	public HarmonySearch() {
		this(20, 0.95, 0.7, 0.05);
	}
	
	public HarmonySearch(int mem_size, double consid_rate, double adjust_rate, double range) {
		this.mem_size = mem_size;
		this.consid_rate = consid_rate;
		this.adjust_rate = adjust_rate;
		this.range = range;
		this.debug = false;
		ai = new AlgorithmInfo("Harmony Search",
				"@book{brownlee2011clever,title={Clever Algorithms: Nature-Inspired Programming Recipes},  author={Brownlee, J.},  isbn={9781446785065},  url={http://books.google.si/books?id=SESWXQphCUkC},  year={2011},  publisher={Lulu.com}}",
				"HS", "Harmony Search based on the description by Yang, with refinement from Geem.");
		au = new Author("mabu", "N/A");
		resetDefaultsBeforNewRun();
		
		ai.addParameter(EnumAlgorithmParameters.POP_SIZE, "" + mem_size);
		ai.addParameter(EnumAlgorithmParameters.CONSIDER, "" + consid_rate);
		ai.addParameter(EnumAlgorithmParameters.PITCH_ADJUSTMENT, "" + adjust_rate);
		ai.addParameter(EnumAlgorithmParameters.PITCH_BANDWITH, "" + range);
	}
	
	public HarmonySearch(boolean d) {
		super();
		setDebug(d);
		random = new Random();
