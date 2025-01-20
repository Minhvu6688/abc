# abc


-- Table: public.cm_customer_request

-- DROP TABLE IF EXISTS public.cm_customer_request;

CREATE TABLE IF NOT EXISTS public.cm_customer_request
(
    id bigint NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 9223372036854775807 CACHE 1 ),
    cm_customer_code character varying(255) COLLATE pg_catalog."default" NOT NULL,
    lading_code character varying(50) COLLATE pg_catalog."default" NOT NULL,
    contact_phone character varying(20) COLLATE pg_catalog."default" NOT NULL,
    request_type integer NOT NULL DEFAULT 0,
    reception_channel integer NOT NULL,
    request_content text COLLATE pg_catalog."default",
    note text COLLATE pg_catalog."default",
    created timestamp without time zone,
    createdby bigint,
    updated timestamp without time zone,
    updatedby bigint,
    isactive boolean DEFAULT true,
    isdeleted boolean DEFAULT false,
    CONSTRAINT cm_customer_request_pk PRIMARY KEY (id)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.cm_customer_request
    OWNER to postgres;

COMMENT ON COLUMN public.cm_customer_request.request_type
    IS '0: Tư vấn | 1: Góp ý | 2: Hỗ trợ';

COMMENT ON COLUMN public.cm_customer_request.reception_channel
    IS '0: Tất cả | 1: •Web/app khách hàng | 2: Mạng xã hội | 3: Website | 4: Mail | 5: Tổng đài 19008095 | 6: BOT | 7: Đơn vị | 8: Chat app | 9: Quốc tế';
