<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>근로계약서 작성 도우미 ✍️</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;600;700&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap'); /* 제목용 폰트 */
        :root {
            /* CSS 변수 기본값 설정 */
            --accent-color: #2563EB; /* 기본 파란색 */
            --accent-color-light: #BFDBFE;
            --accent-color-start: #3B82F6;
            --accent-color-end: #2563EB;
            --header-bg-image: none; /* 기본 이미지 없음 */
            --header-bg-position: center center;
            --header-bg-size: 40% auto;
            --header-bg-opacity: 0.15;
            --header-mix-blend-mode: soft-light;
        }
        * {
            font-family: 'Noto Sans KR', sans-serif;
        }
        .material-section {
            break-inside: avoid;
            page-break-inside: avoid;
            margin-bottom: 2rem;
            padding: 1.5rem;
            background-color: #ffffff; /* 섹션 배경색 */
            border-radius: 0.75rem; /* 둥근 모서리 */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05); /* 은은한 그림자 */
        }
        .input-group {
            margin-bottom: 1rem;
        }
        .section-divider {
            border-top: 2px solid #e5e7eb;
            margin: 3rem 0; /* 간격 확대 */
        }
        .gradient-header-bg {
            /* 양식명에 따른 테마 색상 그라디언트 (기본: blue) */
            background: linear-gradient(135deg, var(--accent-color-start) 0%, var(--accent-color-end) 100%);
            padding: 2.5rem; /* 패딩 증가 */
            border-radius: 1rem; /* 더 둥근 모서리 */
            color: white;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.2); /* 텍스트 그림자 */
            position: relative; /* ::before 가상 요소의 기준점 */
            overflow: hidden; /* 배경 이미지가 박스 밖으로 나가지 않도록 */
            /* 인쇄 시에도 색상 유지를 위해 */
            -webkit-print-color-adjust: exact;
            print-color-adjust: exact;
        }
        /* 헤더 배경 이미지 기본 스타일 (가상 요소) */
        .gradient-header-bg::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: var(--header-bg-image); /* JS에서 설정된 이미지 */
            background-repeat: no-repeat;
            background-position: var(--header-bg-position); /* JS에서 설정된 위치 */
            background-size: var(--header-bg-size); /* JS에서 설정된 크기 */
            opacity: var(--header-bg-opacity); /* JS에서 설정된 투명도 */
            z-index: 1; /* 그라디언트 위에 오도록 */
            mix-blend-mode: var(--header-mix-blend-mode); /* JS에서 설정된 블렌딩 모드 */
            /* 인쇄 시에도 색상 유지를 위해 */
            -webkit-print-color-adjust: exact;
            print-color-adjust: exact;
        }
        .gradient-header-bg h1, .gradient-header-bg p {
            position: relative; /* 텍스트가 이미지 위에 오도록 */
            z-index: 2;
        }
        .accent-border {
            border-left: 5px solid var(--accent-color, #2563EB); /* 테마 색상 경계선 */
            padding-left: 1rem;
        }
        /* H2 및 H3에 동일하게 적용될 섹션 제목 스타일 */
        .section-heading, .document-output h2, .document-output h3 {
            font-family: 'Playfair Display', serif !important; /* Playfair Display 폰트 강제 적용 */
            font-weight: 700 !important; /* 굵게 강제 적용 */
            color: #1F2937 !important; /* 진한 회색 강제 적용 */
            display: flex; /* 아이콘과 텍스트 정렬 */
            align-items: center;
        }
        .section-heading { /* input form의 h3과 output h2에 적용 */
            border-bottom: 3px solid var(--accent-color-light); /* 테마 색상으로 밑줄 */
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
        .section-heading i {
            margin-right: 0.75rem;
            color: var(--accent-color);
            -webkit-print-color-adjust: exact; /* 인쇄 시 색상 유지 */
            print-color-adjust: exact;
        }
        /* PDF 생성 기능 관련 CSS */
        @media print {
            .no-print { display: none !important; }
            .print-only { display: block !important; }
            body {
                -webkit-print-color-adjust: exact; /* Chrome, Safari */
                print-color-adjust: exact; /* 표준 */
                font-size: 10pt; /* 인쇄 시 글꼴 크기 약간 축소 (근로계약서용) */
                line-height: 1.5; /* 인쇄 시 줄간격 (근로계약서용) */
                color: #000000; /* 검은색 텍스트 */
                background-color: transparent !important; /* 배경색 투명하게 */
            }
            .container {
                max-width: 100%;
                padding: 0;
                margin: 0;
            }
            .shadow-lg {
                box-shadow: none !important; /* 전체 그림자 제거 */
            }
            .document-output {
                margin: 0;
                padding: 0;
                width: 100%;
                font-family: 'Noto Sans KR', 'Malgun Gothic', sans-serif !important; /* 인쇄 시 한국어 문서 표준 폰트 */
            }
            .document-output h1, .document-output h2, .document-output h3, .document-output h4 {
                font-family: 'Noto Sans KR', 'Malgun Gothic', sans-serif !important; /* 제목도 동일 폰트 */
                 color: #000000 !important;
            }
            /* material-section의 외곽선과 그림자를 인쇄 시에도 유지 */
            .material-section {
                box-shadow: none !important;
                border: 1px solid #ccc !important;
                padding: 1rem !important;
                margin-bottom: 1rem !important;
                background-color: #ffffff !important;
                border-radius: 0 !important; /* 인쇄시에는 각진 형태로 */
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
            .section-heading { /* 인쇄 시 밑줄 및 마진 재조정 */
                border-bottom: 1px solid #666 !important; /* 인쇄 시 밑줄 얇게 */
                padding-bottom: 0.25rem !important;
                margin-bottom: 0.75rem !important;
                 color: #000000 !important;
            }
             .section-heading i {
                color: var(--accent-color) !important; /* 아이콘 색상 유지 */
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
            /* 그라디언트 헤더 및 색상 요소의 색상 유지 */
            .gradient-header-bg {
                background: linear-gradient(135deg, var(--accent-color-start) 0%, var(--accent-color-end) 100%) !important;
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
                color: white !important;
                padding: 1rem !important;
                border-radius: 0 !important;
                text-shadow: none !important;
                border: none !important;
                 text-align: center !important;
            }
            .gradient-header-bg::before { /* 인쇄 시 배경 이미지도 유지 */
                background-image: var(--header-bg-image) !important;
                background-position: var(--header-bg-position) !important;
                background-size: var(--header-bg-size) !important;
                opacity: 0.03 !important; /* 인쇄 시 더 희미하게 */
                mix-blend-mode: normal !important; /* 인쇄 시 블렌딩 모드 제거하여 호환성 개선 */
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
             .gradient-header-bg h1 {
                font-size: 20pt !important;
                font-weight: bold !important;
                color: white !important;
            }
            .accent-border {
                border-left-color: var(--accent-color) !important;
                background-color: transparent !important; /* 인쇄 시 배경색 제거 */
                -webkit-print-color-adjust: exact !important;
                print-color-adjust: exact !important;
            }
            .table-cell {
                border: 1px solid #ccc;
                padding: 0.5rem;
            }
            p, li, span, strong, div { /* 기본 텍스트 요소들 */
                color: #000000 !important;
            }
        }
        .print-only { display: none; } /* 기본적으로 숨김 */
        @page {
            size: A4;
            margin: 2cm; /* A4 용지 여백 조정 */
        }
        /* 입력 필드 디자인 개선 */
        label {
            font-weight: 500;
        }
        input[type="text"], input[type="date"], input[type="time"], input[type="number"], select, textarea {
            border-color: #D1D5DB; /* 기본 테두리 색상 */
            transition: all 0.15s ease-in-out;
        }
        input[type="text"]:focus, input[type="date"]:focus, input[type="time"]:focus, input[type="number"]:focus, select:focus, textarea:focus {
            border-color: var(--accent-color);
            box-shadow: 0 0 0 2px var(--accent-color-light);
        }
        /* 테이블 레이아웃을 위한 스타일 (미리보기용) */
        .preview-table { width: 100%; border-collapse: collapse; margin-bottom: 1rem; }
        .preview-table th, .preview-table td { border: 1px solid #e2e8f0; padding: 0.75rem; text-align: left; vertical-align: top;}
        .preview-table th { background-color: #f7fafc; font-weight: 600; }
        .preview-table p { margin-bottom: 0.25rem; }
        .preview-table strong { font-weight: 500; }
        /* Fade-in animation for preview */
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .fade-in { animation: fadeIn 0.5s ease-out forwards; }
    </style>
</head>
<body class="bg-gray-50 min-h-screen">
    <div class="container mx-auto px-4 py-8 max-w-7xl">
        <div class="text-center mb-8 no-print">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">
                <i class="fas fa-file-signature text-blue-600 mr-3"></i> 근로계약서 작성 도우미
            </h1>
            <p class="text-gray-600 text-lg">아래 정보를 입력하시면 표준 근로계약서가 자동 생성됩니다.</p>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
            <div class="bg-white rounded-lg shadow-lg p-6 no-print">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">
                    <i class="fas fa-edit text-blue-500 mr-2"></i>
                    정보 입력
                </h2>
                <form id="documentForm" class="space-y-6">
                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-file-alt"></i> 계약 기본 정보
                        </h3>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="documentTitle">계약서 제목*</label>
                            <input type="text" id="documentTitle" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 표준 근로계약서">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="contractDate">계약 체결일*</label>
                            <input type="date" id="contractDate" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-building"></i> 사업주 정보 (갑)
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="employerCompanyName">회사명*</label>
                                <input type="text" id="employerCompanyName" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: (주)미래컴퍼니">
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="employerRepresentativeName">대표자명*</label>
                                <input type="text" id="employerRepresentativeName" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 홍길동">
                            </div>
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="employerBusinessNumber">사업자등록번호</label>
                            <input type="text" id="employerBusinessNumber" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 123-45-67890">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="employerCompanyAddress">회사 주소*</label>
                            <input type="text" id="employerCompanyAddress" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 서울특별시 강남구 테헤란로 123, 4층">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="employerCompanyContact">회사 연락처</label>
                            <input type="text" id="employerCompanyContact" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 02-1234-5678">
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-user"></i> 근로자 정보 (을)
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="employeeName">성명*</label>
                                <input type="text" id="employeeName" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 김근로">
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="employeeBirthDate">생년월일*</label>
                                <input type="date" id="employeeBirthDate" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                            </div>
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="employeeContact">연락처*</label>
                            <input type="text" id="employeeContact" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 010-9876-5432">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="employeeAddress">주소*</label>
                            <input type="text" id="employeeAddress" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 경기도 성남시 분당구 판교역로 456">
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-briefcase"></i> 근로 조건
                        </h3>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="contractType">계약 구분*</label>
                            <select id="contractType" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                                <option value="기간의 정함이 없는 근로계약">기간의 정함이 없는 근로계약</option>
                                <option value="기간제 근로계약">기간제 근로계약</option>
                            </select>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="contractStartDate">근로 시작일*</label>
                                <input type="date" id="contractStartDate" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="contractEndDate">근로 종료일 (기간제인 경우)</label>
                                <input type="date" id="contractEndDate" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                            </div>
                        </div>
                         <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="workplace">근무 장소*</label>
                            <input type="text" id="workplace" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 본사 사무실 (서울특별시 강남구 테헤란로 123)">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="jobDescription">업무 내용*</label>
                            <textarea id="jobDescription" rows="3" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 소프트웨어 개발 및 유지보수, 마케팅 전략 수립 및 실행 등 구체적으로 기재"></textarea>
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-clock"></i> 근로시간 및 휴게
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="workStartTime">시업 시간*</label>
                                <input type="time" id="workStartTime" required value="09:00" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="workEndTime">종업 시간*</label>
                                <input type="time" id="workEndTime" required value="18:00" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                            </div>
                             <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="breakTime">휴게 시간*</label>
                                <input type="text" id="breakTime" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 12:00 ~ 13:00 (1시간)">
                            </div>
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="workDays">근무일*</label>
                            <input type="text" id="workDays" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 매주 월요일부터 금요일까지 (주 5일)">
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="weeklyHoliday">주휴일*</label>
                            <input type="text" id="weeklyHoliday" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 매주 일요일">
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-won-sign"></i> 임금
                        </h3>
                         <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="salaryType">임금 형태*</label>
                                <select id="salaryType" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2">
                                    <option value="월급">월급</option>
                                    <option value="연봉">연봉</option>
                                    <option value="시급">시급</option>
                                </select>
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="salaryAmount">임금액 (세전)*</label>
                                <input type="number" id="salaryAmount" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 3000000">
                            </div>
                        </div>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="salaryComponents">임금 구성항목</label>
                            <textarea id="salaryComponents" rows="3" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 기본급: 2,500,000원, 직책수당: 200,000원, 식대보조비: 100,000원, 주휴수당 별도 명시 또는 포함 여부 등"></textarea>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="salaryPaymentDate">임금 지급일*</label>
                                <input type="text" id="salaryPaymentDate" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 매월 25일">
                            </div>
                            <div class="input-group">
                                <label class="block text-sm font-medium text-gray-700 mb-1" for="salaryPaymentMethod">임금 지급방법*</label>
                                <input type="text" id="salaryPaymentMethod" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 근로자 명의의 예금계좌로 입금 (OO은행 123-456-789012)">
                            </div>
                        </div>
                    </div>

                    <div class="border-b border-gray-200 pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-umbrella-beach"></i> 연차유급휴가 및 사회보험
                        </h3>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="annualLeave">연차유급휴가*</label>
                            <textarea id="annualLeave" rows="2" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 근로기준법에서 정하는 바에 따름"></textarea>
                        </div>
                         <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="socialInsurance">사회보험 적용*</label>
                            <textarea id="socialInsurance" rows="2" required class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 국민연금, 건강보험, 고용보험, 산재보험 가입"></textarea>
                        </div>
                    </div>
                    
                    <div class="pb-6">
                        <h3 class="text-lg font-semibold text-gray-700 mb-4 section-heading">
                            <i class="fas fa-ellipsis-h"></i> 기타 근로조건
                        </h3>
                        <div class="input-group">
                            <label class="block text-sm font-medium text-gray-700 mb-1" for="otherConditions">기타사항</label>
                            <textarea id="otherConditions" rows="3" class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2" placeholder="예: 수습기간(해당 시 명시, 예: 3개월, 수습기간 중 급여는 정규 급여의 90% 지급), 근로계약서에서 정하지 아니한 사항은 근로기준법 및 관계 법령에 따름."></textarea>
                        </div>
                    </div>

                    <div class="flex flex-col space-y-3">
                        <button type="submit" class="w-full bg-blue-600 text-white py-3 px-6 rounded-md hover:bg-blue-700 transition duration-300 font-semibold">
                            <i class="fas fa-magic mr-2"></i>
                            근로계약서 생성하기
                        </button>
                        <button type="button" id="saveFileButton" class="w-full bg-blue-500 text-white py-3 px-6 rounded-md hover:bg-blue-600 transition duration-300 font-semibold">
                            <i class="fas fa-download mr-2"></i>
                            데이터 파일로 저장
                        </button>
                        <label for="loadFile" class="w-full bg-gray-500 text-white py-3 px-6 rounded-md hover:bg-gray-600 transition duration-300 font-semibold text-center cursor-pointer">
                            <i class="fas fa-upload mr-2"></i>
                            데이터 파일 불러오기
                            <input type="file" id="loadFile" accept=".json" class="hidden">
                        </label>
                        <button type="button" id="clearFormButton" class="w-full bg-gray-300 text-gray-800 py-3 px-6 rounded-md hover:bg-gray-400 transition duration-300 font-semibold">
                            <i class="fas fa-trash-alt mr-2"></i>
                            양식 초기화
                        </button>
                    </div>
                </form>
            </div>
            <div class="bg-white rounded-lg shadow-lg p-8">
                <div class="flex items-center justify-between mb-6 no-print">
                    <h2 class="text-2xl font-bold text-gray-800">
                        <i class="fas fa-file-alt text-green-600 mr-2"></i>
                        생성된 근로계약서
                    </h2>
                    <button onclick="window.print()" class="bg-green-600 text-white px-4 py-2 rounded-md hover:bg-green-700 transition duration-300">
                        <i class="fas fa-print mr-2"></i>
                        PDF 저장
                    </button>
                </div>
                <div id="documentPreview" class="document-output">
                    <div class="text-center text-gray-500 py-12">
                        <i class="fas fa-clipboard-list text-6xl mb-4"></i>
                        <p class="text-lg">좌측 양식을 작성하고 "근로계약서 생성하기" 버튼을 클릭하세요</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script>
        const formId = 'documentForm'; 
        const localStorageKeyPrefix = 'form_generator_'; 
        function saveFormDataToLocalStorage() {
            const formData = {};
            const formElements = document.querySelectorAll(`#${formId} input, #${formId} textarea, #${formId} select`);
            formElements.forEach(element => {
                if (element.id) { 
                    formData[element.id] = element.value;
                }
            });
            localStorage.setItem(localStorageKeyPrefix + formId, JSON.stringify(formData));
        }
        function loadFormDataFromLocalStorage() {
            const savedData = localStorage.getItem(localStorageKeyPrefix + formId);
            if (savedData) {
                const formData = JSON.parse(savedData);
                for (const id in formData) {
                    const element = document.getElementById(id);
                    if (element) {
                        if (element.type === 'date') {
                            if (formData[id]) {
                                element.valueAsDate = new Date(formData[id]);
                            }
                        } else {
                            element.value = formData[id];
                        }
                    }
                }
                generateDocument();
            } else {
                const contractDateElement = document.getElementById('contractDate');
                 if (contractDateElement && !contractDateElement.value) {
                    const today = new Date();
                    contractDateElement.value = today.toISOString().slice(0,10);
                }
                const contractStartDateElement = document.getElementById('contractStartDate');
                 if (contractStartDateElement && !contractStartDateElement.value) {
                    const today = new Date();
                    contractStartDateElement.value = today.toISOString().slice(0,10);
                }
                // 기본 플레이스홀더 값 설정 (예시)
                const defaultPlaceholders = {
                    'documentTitle': '표준 근로계약서',
                    'workStartTime': '09:00',
                    'workEndTime': '18:00',
                    'breakTime': '12:00 ~ 13:00 (1시간)',
                    'workDays': '매주 월요일부터 금요일까지 (주 5일)',
                    'weeklyHoliday': '매주 일요일',
                    'annualLeave': '근로기준법에서 정하는 바에 따름',
                    'socialInsurance': '국민연금, 건강보험, 고용보험, 산재보험 가입'
                };
                for (const id in defaultPlaceholders) {
                    const element = document.getElementById(id);
                    if (element && !element.value) { // 이미 값이 없는 경우에만 설정
                        element.value = defaultPlaceholders[id];
                    }
                }
                generateDocument();
            }
        }
        function clearForm() {
            const formElements = document.querySelectorAll(`#${formId} input, #${formId} textarea, #${formId} select`);
            formElements.forEach(element => {
                if (element.type === 'date') {
                    element.value = ''; 
                } else if (element.tagName === 'SELECT') {
                    element.selectedIndex = 0; // select 박스는 첫 번째 옵션으로
                } else {
                    element.value = ''; 
                }
            });
            localStorage.removeItem(localStorageKeyPrefix + formId); 
            loadFormDataFromLocalStorage(); // 기본값으로 다시 로드
        }
        function downloadDataFile() {
            const formData = {};
            const formElements = document.querySelectorAll(`#${formId} input, #${formId} textarea, #${formId} select`);
            formElements.forEach(element => {
                if (element.id) {
                    formData[element.id] = element.value;
                }
            });
            const dataStr = JSON.stringify(formData, null, 2); 
            const blob = new Blob([dataStr], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            const formTitle = (document.getElementById('documentTitle').value || '근로계약서').replace(/[^a-zA-Z0-9가-힣_]/g, '_');
            a.download = `${formTitle}_데이터_${new Date().toISOString().slice(0,10)}.json`; 
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        }
        function uploadDataFile(event) {
            const file = event.target.files[0];
            if (!file) {
                return;
            }
            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const loadedData = JSON.parse(e.target.result);
                    for (const id in loadedData) {
                        const element = document.getElementById(id);
                        if (element) {
                            if (element.type === 'date') {
                                if (loadedData[id]) {
                                    element.valueAsDate = new Date(loadedData[id]);
                                }
                            } else {
                                element.value = loadedData[id];
                            }
                        }
                    }
                    saveFormDataToLocalStorage(); 
                    generateDocument(); 
                    alert('데이터를 성공적으로 불러왔습니다!');
                } catch (error) {
                    alert('파일을 읽는 중 오류가 발생했거나 유효한 JSON 파일이 아닙니다: ' + error.message);
                }
            };
            reader.readAsText(file);
            event.target.value = '';
        }

        function nl2p(str) {
            if (!str) return '';
            return str.split('\n').map(s => `<p class="text-gray-700 leading-relaxed mb-1">${s || '&nbsp;'}</p>`).join('');
        }
        
        function formatCurrency(numStr) {
            if (!numStr) return '0';
            const num = parseInt(numStr, 10);
            if (isNaN(num)) return numStr; // 숫자가 아니면 원래 문자열 반환
            return num.toLocaleString('ko-KR');
        }

        function generateDocument() {
            const getValue = id => document.getElementById(id).value || (document.getElementById(id).placeholder || '');
            const getDateValue = id => {
                const val = document.getElementById(id).value;
                return val ? new Date(val).toLocaleDateString('ko-KR', { year: 'numeric', month: 'long', day: 'numeric' }) : '미기재';
            };
            const getTimeValue = id => {
                 const val = document.getElementById(id).value;
                 if (!val) return '미기재';
                 const [hours, minutes] = val.split(':');
                 return `${parseInt(hours, 10)}시 ${parseInt(minutes, 10)}분`;
            };

            const documentTitle = getValue('documentTitle');
            const contractDate = getDateValue('contractDate');
            
            const employerCompanyName = getValue('employerCompanyName');
            const employerRepresentativeName = getValue('employerRepresentativeName');
            const employerBusinessNumber = getValue('employerBusinessNumber');
            const employerCompanyAddress = getValue('employerCompanyAddress');
            const employerCompanyContact = getValue('employerCompanyContact');

            const employeeName = getValue('employeeName');
            const employeeBirthDate = getDateValue('employeeBirthDate');
            const employeeContact = getValue('employeeContact');
            const employeeAddress = getValue('employeeAddress');

            const contractType = getValue('contractType');
            const contractStartDate = getDateValue('contractStartDate');
            const contractEndDateInput = document.getElementById('contractEndDate').value;
            const contractEndDate = contractType === '기간제 근로계약' && contractEndDateInput ? getDateValue('contractEndDate') : '기간의 정함이 없음';
            
            const workplace = getValue('workplace');
            const jobDescription = getValue('jobDescription');

            const workStartTime = getTimeValue('workStartTime');
            const workEndTime = getTimeValue('workEndTime');
            const breakTime = getValue('breakTime');
            const workDays = getValue('workDays');
            const weeklyHoliday = getValue('weeklyHoliday');

            const salaryType = getValue('salaryType');
            const salaryAmount = formatCurrency(getValue('salaryAmount'));
            const salaryComponents = getValue('salaryComponents');
            const salaryPaymentDate = getValue('salaryPaymentDate');
            const salaryPaymentMethod = getValue('salaryPaymentMethod');

            const annualLeave = getValue('annualLeave');
            const socialInsurance = getValue('socialInsurance');
            const otherConditions = getValue('otherConditions');

            const root = document.documentElement;
            let themeColor = '#1D4ED8'; // 차분한 파란색 (신뢰)
            let themeColorLight = '#DBEAFE';
            let themeColorStart = '#3B82F6';
            let themeColorEnd = '#1D4ED8';
            let headerBgImage = "url('https://images.unsplash.com/photo-1556761175-5973dc0f32e7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8YnVzaW5lc3MlMjBoYW5kc2hha2V8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60')"; // 악수 또는 계약 관련 이미지
            let headerBgPosition = 'center 20%';
            let headerBgSize = 'cover';
            let headerBgOpacity = 0.08;
            let headerMixBlendMode = 'luminosity';

            root.style.setProperty('--accent-color', themeColor);
            root.style.setProperty('--accent-color-light', themeColorLight);
            root.style.setProperty('--accent-color-start', themeColorStart);
            root.style.setProperty('--accent-color-end', themeColorEnd);
            root.style.setProperty('--header-bg-image', headerBgImage);
            root.style.setProperty('--header-bg-position', headerBgPosition);
            root.style.setProperty('--header-bg-size', headerBgSize);
            root.style.setProperty('--header-bg-opacity', headerBgOpacity);
            root.style.setProperty('--header-mix-blend-mode', headerMixBlendMode);

            let generatedHtml = `
                <div class="fade-in">
                    <div class="gradient-header-bg text-center mb-8">
                        <h1 class="text-3xl md:text-4xl font-bold mb-2">${documentTitle}</h1>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-users"></i>제1조 (근로계약 당사자)</h2>
                        <table class="preview-table">
                            <tr>
                                <th style="width:15%;">구분</th>
                                <th style="width:42.5%;">사업주 (갑)</th>
                                <th style="width:42.5%;">근로자 (을)</th>
                            </tr>
                            <tr>
                                <td><strong>회사명</strong></td>
                                <td>${employerCompanyName}</td>
                                <td rowspan="2"><strong>성명</strong><br>${employeeName}</td>
                            </tr>
                            <tr>
                                <td><strong>대표자</strong></td>
                                <td>${employerRepresentativeName}</td>
                            </tr>
                             <tr>
                                <td><strong>사업자번호</strong></td>
                                <td>${employerBusinessNumber || '해당 없음'}</td>
                                <td><strong>생년월일</strong><br>${employeeBirthDate}</td>
                            </tr>
                            <tr>
                                <td><strong>소재지</strong></td>
                                <td>${employerCompanyAddress}</td>
                                <td><strong>주소</strong><br>${employeeAddress}</td>
                            </tr>
                            <tr>
                                <td><strong>연락처</strong></td>
                                <td>${employerCompanyContact || '미기재'}</td>
                                <td><strong>연락처</strong><br>${employeeContact}</td>
                            </tr>
                        </table>
                        <p class="text-sm text-gray-600 mt-2">위 사업주(이하 "갑"이라 함)와 근로자(이하 "을"이라 함)는 다음과 같이 근로계약을 체결하고 이를 성실히 이행할 것을 약정한다.</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-calendar-alt"></i>제2조 (근로계약기간)</h2>
                        <p>1. 계약 구분: ${contractType}</p>
                        <p>2. 근로계약 시작일: ${contractStartDate}</p>
                        <p>3. 근로계약 종료일: ${contractEndDate}</p>
                        ${contractType === '기간제 근로계약' ? '<p class="text-sm text-gray-500 mt-1">(기간제 근로자의 경우 계약기간 만료로 근로관계는 자동 종료됨)</p>' : ''}
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-map-marker-alt"></i>제3조 (근무 장소)</h2>
                        <p>${nl2p(workplace)}</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-briefcase"></i>제4조 (업무의 내용)</h2>
                        <p>${nl2p(jobDescription)}</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-clock"></i>제5조 (소정근로시간 및 휴게)</h2>
                        <p>1. 소정근로시간: ${workStartTime}부터 ${workEndTime}까지 (1일 ${ (new Date(`1970-01-01T${document.getElementById('workEndTime').value}:00Z`).getTime() - new Date(`1970-01-01T${document.getElementById('workStartTime').value}:00Z`).getTime()) / (1000 * 60 * 60) - (breakTime.includes("1시간")?1:(breakTime.includes("30분")?0.5:0)) }시간)</p>
                        <p>2. 휴게시간: ${breakTime}</p>
                    </div>
                    
                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-calendar-day"></i>제6조 (근무일 및 휴일)</h2>
                        <p>1. 근무일: ${workDays}</p>
                        <p>2. 주휴일: ${weeklyHoliday}</p>
                        <p class="text-sm text-gray-500 mt-1">(회사의 사정에 따라 근무일 및 주휴일은 변경될 수 있으며, 이 경우 사전에 통보한다.)</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-won-sign"></i>제7조 (임금)</h2>
                        <p>1. 임금형태: ${salaryType}</p>
                        <p>2. 임금액: ${salaryType === '시급' ? `시급 ${salaryAmount}원` : `${salaryType} ${salaryAmount}원`} (세전)</p>
                        <p>3. 임금 구성항목: ${nl2p(salaryComponents) || '기본급 및 제수당 포함. 상세내역은 급여명세서에 의함.'}</p>
                        <p>4. 임금 지급일: ${salaryPaymentDate} (단, 지급일이 공휴일인 경우 그 전일에 지급)</p>
                        <p>5. 임금 지급방법: ${salaryPaymentMethod}</p>
                        <p class="text-sm text-gray-500 mt-1">(회사는 "을"의 동의 없이 임금에서 공제할 수 있는 것은 관계법령에서 정한 것에 한한다.)</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-umbrella-beach"></i>제8조 (연차유급휴가)</h2>
                        <p>${nl2p(annualLeave)}</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-shield-alt"></i>제9조 (사회보험 및 복리후생)</h2>
                         <p>1. 사회보험: ${nl2p(socialInsurance)}</p>
                         <p>2. 기타 복리후생은 회사의 취업규칙 및 관련 규정에 따른다.</p>
                    </div>
                    
                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-file-contract"></i>제10조 (근로계약서 교부)</h2>
                        <p>"갑"은 근로계약을 체결함과 동시에 본 계약서를 사본하여 "을"의 교부 요구와 관계없이 "을"에게 교부한다. (근로기준법 제17조)</p>
                    </div>

                    <div class="material-section">
                        <h2 class="section-heading text-xl"><i class="fas fa-gavel"></i>제11조 (기타)</h2>
                        <p>이 계약에 정함이 없는 사항은 근로기준법, 산업안전보건법 등 노동관계법령, 단체협약, 취업규칙 및 회사의 관련 규정이 정하는 바에 따른다.</p>
                        ${otherConditions ? `<div class="mt-2 accent-border p-3 bg-gray-50 rounded">${nl2p(otherConditions)}</div>` : ''}
                    </div>

                    <div class="material-section text-center mt-8 pt-4">
                        <p class="mb-6">본 계약을 증명하기 위하여 계약서 2부를 작성하여 "갑"과 "을"이 각각 1부씩 보관한다.</p>
                        <p class="mb-12 text-lg"><strong>계약 체결일:</strong> ${contractDate}</p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 pt-8 border-t">
                            <div>
                                <p class="font-semibold text-lg mb-2">(갑) 사업주</p>
                                <p>회사명: ${employerCompanyName}</p>
                                <p>대표자: ${employerRepresentativeName} (서명/인)</p>
                                <div style="height: 50px; border-bottom: 1px solid #ccc; margin-top: 20px; margin-left: auto; margin-right: auto; max-width: 200px;"></div>
                            </div>
                            <div>
                                <p class="font-semibold text-lg mb-2">(을) 근로자</p>
                                <p>성명: ${employeeName} (서명/인)</p>
                                <div style="height: 50px; border-bottom: 1px solid #ccc; margin-top: 20px; margin-left: auto; margin-right: auto; max-width: 200px;"></div>
                            </div>
                        </div>
                    </div>

                    <div class="text-center text-gray-500 text-sm mt-8 pt-4 border-t border-gray-300 print-only">
                        <p>본 문서는 ${new Date().toLocaleDateString('ko-KR')}에 생성되었습니다.</p>
                    </div>
                </div>
            `;
            document.getElementById('documentPreview').innerHTML = generatedHtml;
            
            if (window.innerWidth < 1024 && document.activeElement.form) { // 입력 중일 때만 스크롤
                document.getElementById('documentPreview').scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        }
        function setupInputPlaceholders() {
            const inputs = document.querySelectorAll('#documentForm input[placeholder], #documentForm textarea[placeholder]');
            inputs.forEach(input => {
                input.addEventListener('keydown', (e) => {
                    if (e.key === 'Tab' && input.value.trim() === '' && input.placeholder) {
                        e.preventDefault(); 
                        input.value = input.placeholder;
                        saveFormDataToLocalStorage(); 
                        generateDocument(); 
                    }
                });
            });
        }
        document.addEventListener('DOMContentLoaded', function() {
            setupInputPlaceholders(); 
            loadFormDataFromLocalStorage(); 
            const formElements = document.querySelectorAll(`#${formId} input, #${formId} textarea, #${formId} select`);
            formElements.forEach(element => {
                element.addEventListener('input', () => {
                    saveFormDataToLocalStorage();
                    generateDocument(); 
                });
                element.addEventListener('change', () => { 
                    saveFormDataToLocalStorage();
                    generateDocument(); 
                });
            });
            document.getElementById('saveFileButton').addEventListener('click', downloadDataFile);
            document.getElementById('loadFile').addEventListener('change', uploadDataFile);
            document.getElementById('clearFormButton').addEventListener('click', clearForm); 
            document.getElementById('documentForm').addEventListener('submit', function(e) {
                e.preventDefault();
                generateDocument();
            });
        });
    </script>
</body>
</html>
